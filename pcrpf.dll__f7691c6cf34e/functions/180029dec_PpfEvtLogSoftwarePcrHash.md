# PpfEvtLogSoftwarePcrHash

- ea: `0x180029dec`
- end: `0x180029f94`
- name: `PpfEvtLogSoftwarePcrHash`
- size: `424`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180029ccc`
- `0x18002d0f8`

## callees

- `0x18001df80`
- `0x18001dfd8`
- `0x1800290f4`
- `0x180029dec`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x180029e9a`
- `bcrypt!BCryptHashData` at `0x180029e9a`

## string_xrefs

- `0x180029ebc`: `TpmApiShaUpdate failed: 0x%x`

## pseudocode

```c
__int64 __fastcall PpfEvtLogSoftwarePcrHash(__int64 a1, UCHAR *a2, ULONG a3, __int64 a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  NTSTATUS v10; // eax
  int v11; // eax
  int v12; // eax
  BCRYPT_HASH_HANDLE hHash; // [rsp+60h] [rbp+8h] BYREF

  hHash = 0;
  if ( a1 && a2 && a3 && a4 )
  {
    v8 = TpmApiShaInit(*(LPCWSTR *)(a1 + 8), &hHash, (volatile signed __int64 *)(a1 + 16));
    if ( v8 >= 0 )
    {
      v10 = BCryptHashData(hHash, a2, a3, 0);
      if ( v10 >= 0 || (v11 = v10 | 0x10000000, v11 >= 0) )
      {
        v12 = TpmApiShaFinal(&hHash, a4, *(unsigned __int16 *)(a1 + 2));
        if ( v12 >= 0 )
        {
          return 0;
        }
        else
        {
          PpfEvtLogTraceHelper(
            (int)"minkernel\\ngscb\\ppfevtlog\\pcr.c",
            183,
            (int)"PpfEvtLogSoftwarePcrHash",
            1,
            "TpmApiShaFinal failed: 0x%x",
            v12);
          v9 = -1073741595;
          PpfEvtLogTraceHelper(
            (int)"minkernel\\ngscb\\ppfevtlog\\pcr.c",
            184,
            (int)"PpfEvtLogSoftwarePcrHash",
            1,
            "Error: 0x%x",
            229);
        }
      }
      else
      {
        PpfEvtLogTraceHelper(
          (int)"minkernel\\ngscb\\ppfevtlog\\pcr.c",
          177,
          (int)"PpfEvtLogSoftwarePcrHash",
          1,
          "TpmApiShaUpdate failed: 0x%x",
          v11);
        v9 = -1073741595;
        PpfEvtLogTraceHelper(
          (int)"minkernel\\ngscb\\ppfevtlog\\pcr.c",
          178,
          (int)"PpfEvtLogSoftwarePcrHash",
          1,
          "Error: 0x%x",
          229);
      }
    }
    else
    {
      PpfEvtLogTraceHelper(
        (int)"minkernel\\ngscb\\ppfevtlog\\pcr.c",
        171,
        (int)"PpfEvtLogSoftwarePcrHash",
        1,
        "TpmApiShaInit failed: 0x%x",
        v8);
      v9 = -1073741595;
      PpfEvtLogTraceHelper(
        (int)"minkernel\\ngscb\\ppfevtlog\\pcr.c",
        172,
        (int)"PpfEvtLogSoftwarePcrHash",
        1,
        "Error: 0x%x",
        229);
    }
  }
  else
  {
    v9 = -1073741811;
    PpfEvtLogTraceHelper(
      (int)"minkernel\\ngscb\\ppfevtlog\\pcr.c",
      166,
      (int)"PpfEvtLogSoftwarePcrHash",
      1,
      "Error: 0x%x",
      13);
  }
  return v9;
}

```

## disassembly

```asm
0x180029dec  push    rbx
0x180029dee  push    rbp
0x180029def  push    rsi
0x180029df0  push    rdi
0x180029df1  sub     rsp, 38h
0x180029df5  mov     [rsp+58h+hHash], 0
0x180029dfe  mov     rdi, r9
0x180029e01  mov     esi, r8d
0x180029e04  mov     rbp, rdx
0x180029e07  mov     rbx, rcx
0x180029e0a  test    rcx, rcx
0x180029e0d  jz      loc_180029F55
0x180029e13  test    rdx, rdx
0x180029e16  jz      loc_180029F55
0x180029e1c  test    r8d, r8d
0x180029e1f  jz      loc_180029F55
0x180029e25  test    r9, r9
0x180029e28  jz      loc_180029F55
0x180029e2e  lea     r8, [rcx+10h]
0x180029e32  mov     rcx, [rcx+8]; pszAlgId
0x180029e36  lea     rdx, [rsp+58h+hHash]; phHash
0x180029e3b  call    TpmApiShaInit
0x180029e40  test    eax, eax
0x180029e42  jns     short loc_180029E8C
0x180029e44  mov     dword ptr [rsp+58h+var_30], eax; char
0x180029e48  lea     r8, aPpfevtlogsoftw_2; "PpfEvtLogSoftwarePcrHash"
0x180029e4f  lea     rax, aTpmapishainitF; "TpmApiShaInit failed: 0x%x"
0x180029e56  mov     edi, 1
0x180029e5b  mov     r9d, edi; int
0x180029e5e  mov     [rsp+58h+Format], rax; Format
0x180029e63  mov     edx, 0ABh; int
0x180029e68  lea     rcx, aMinkernelNgscb_0; "minkernel\\ngscb\\ppfevtlog\\pcr.c"
0x180029e6f  call    PpfEvtLogTraceHelper
0x180029e74  mov     eax, 0C00000E5h
0x180029e79  mov     r9d, edi
0x180029e7c  mov     ebx, eax
0x180029e7e  mov     dword ptr [rsp+58h+var_30], eax
0x180029e82  mov     edx, 0ACh
0x180029e87  jmp     loc_180029F69
0x180029e8c  mov     rcx, [rsp+58h+hHash]; hHash
0x180029e91  xor     r9d, r9d; dwFlags
0x180029e94  mov     r8d, esi; cbInput
0x180029e97  mov     rdx, rbp; pbInput
0x180029e9a  call    cs:__imp_BCryptHashData
0x180029ea1  nop     dword ptr [rax+rax+00h]
0x180029ea6  test    eax, eax
0x180029ea8  jns     short loc_180029EF6
0x180029eaa  or      eax, 10000000h
0x180029eaf  jge     short loc_180029EF6
0x180029eb1  mov     dword ptr [rsp+58h+var_30], eax; char
0x180029eb5  lea     r8, aPpfevtlogsoftw_2; "PpfEvtLogSoftwarePcrHash"
0x180029ebc  lea     rax, aTpmapishaupdat; "TpmApiShaUpdate failed: 0x%x"
0x180029ec3  mov     edi, 1
0x180029ec8  mov     r9d, edi; int
0x180029ecb  mov     [rsp+58h+Format], rax; Format
0x180029ed0  mov     edx, 0B1h; int
0x180029ed5  lea     rcx, aMinkernelNgscb_0; "minkernel\\ngscb\\ppfevtlog\\pcr.c"
0x180029edc  call    PpfEvtLogTraceHelper
0x180029ee1  mov     eax, 0C00000E5h
0x180029ee6  mov     r9d, edi
0x180029ee9  mov     ebx, eax
0x180029eeb  mov     dword ptr [rsp+58h+var_30], eax
0x180029eef  mov     edx, 0B2h
0x180029ef4  jmp     short loc_180029F69
0x180029ef6  movzx   r8d, word ptr [rbx+2]
0x180029efb  lea     rcx, [rsp+58h+hHash]
0x180029f00  mov     rdx, rdi
0x180029f03  call    TpmApiShaFinal
0x180029f08  test    eax, eax
0x180029f0a  jns     short loc_180029F51
0x180029f0c  mov     dword ptr [rsp+58h+var_30], eax; char
0x180029f10  lea     r8, aPpfevtlogsoftw_2; "PpfEvtLogSoftwarePcrHash"
0x180029f17  lea     rax, aTpmapishafinal; "TpmApiShaFinal failed: 0x%x"
0x180029f1e  mov     edi, 1
0x180029f23  mov     r9d, edi; int
0x180029f26  mov     [rsp+58h+Format], rax; Format
0x180029f2b  mov     edx, 0B7h; int
0x180029f30  lea     rcx, aMinkernelNgscb_0; "minkernel\\ngscb\\ppfevtlog\\pcr.c"
0x180029f37  call    PpfEvtLogTraceHelper
0x180029f3c  mov     eax, 0C00000E5h
0x180029f41  mov     r9d, edi
0x180029f44  mov     ebx, eax
0x180029f46  mov     dword ptr [rsp+58h+var_30], eax
0x180029f4a  mov     edx, 0B8h
0x180029f4f  jmp     short loc_180029F69
0x180029f51  xor     ebx, ebx
0x180029f53  jmp     short loc_180029F88
0x180029f55  mov     ebx, 0C000000Dh
0x180029f5a  mov     r9d, 1; int
0x180029f60  mov     dword ptr [rsp+58h+var_30], ebx; char
0x180029f64  mov     edx, 0A6h; int
0x180029f69  lea     rax, aError0xX; "Error: 0x%x"
0x180029f70  lea     r8, aPpfevtlogsoftw_2; "PpfEvtLogSoftwarePcrHash"
0x180029f77  mov     [rsp+58h+Format], rax; Format
0x180029f7c  lea     rcx, aMinkernelNgscb_0; "minkernel\\ngscb\\ppfevtlog\\pcr.c"
0x180029f83  call    PpfEvtLogTraceHelper
0x180029f88  mov     eax, ebx
0x180029f8a  add     rsp, 38h
0x180029f8e  pop     rdi
0x180029f8f  pop     rsi
0x180029f90  pop     rbp
0x180029f91  pop     rbx
0x180029f92  retn
```
