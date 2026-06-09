# PsmpQueryClientApplicationInformation

- ea: `0x180003ec8`
- end: `0x180004169`
- name: `PsmpQueryClientApplicationInformation`
- size: `673`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, HANDLE TokenHandle, _OWORD *, __int64 *)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180003af0`
- `0x1800180d0`
- `0x18001e20c`
- `0x180023ae8`

## callees

- `0x180003ec8`
- `0x18000463c`
- `0x1800137a4`
- `0x180014cc0`
- `0x180015bb0`
- `0x1800192fc`
- `0x18001b7e0`
- `0x18001c10c`

## import_xrefs

- `ntdll!NtClose` at `0x18000413e`
- `ntdll!NtClose` at `0x18000413e`
- `ntdll!NtOpenProcessTokenEx` at `0x180003f3b`
- `ntdll!NtOpenProcessTokenEx` at `0x180003f3b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800040e9`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800040e9`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x180003f94`
- `api-ms-win-core-psm-key-l1-1-0!PsmGetKeyFromToken` at `0x180003f94`

## pseudocode

```c
__int64 __fastcall PsmpQueryClientApplicationInformation(
        HANDLE ProcessHandle,
        HANDLE TokenHandle,
        _OWORD *a3,
        __int64 *a4)
{
  __int64 v8; // r15
  NTSTATUS ClientInformation; // ebx
  __int64 v10; // r8
  HANDLE v11; // rdx
  int v12; // edx
  char v13; // al
  __int64 v14; // rdi
  _OWORD *v15; // rax
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm1
  DWORD ProcessId; // eax
  NTSTATUS v26; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandlea; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE v33[533]; // [rsp+68h] [rbp-98h] BYREF
  char v34; // [rsp+27Dh] [rbp+17Dh]
  char v35[32]; // [rsp+280h] [rbp+180h] BYREF
  NTSTATUS *v36; // [rsp+2A0h] [rbp+1A0h]
  __int64 v37; // [rsp+2A8h] [rbp+1A8h]
  __int64 *v38; // [rsp+2B0h] [rbp+1B0h]
  __int64 v39; // [rsp+2B8h] [rbp+1B8h]

  memset_0(v31, 0, 0x220u);
  v8 = -1;
  TokenHandlea = 0;
  v28 = -1;
  v29 = 0;
  if ( TokenHandle )
  {
    v11 = TokenHandle;
    TokenHandlea = TokenHandle;
  }
  else
  {
    ClientInformation = NtOpenProcessTokenEx(ProcessHandle, 8u, 0, &TokenHandlea);
    if ( ClientInformation < 0 )
      goto LABEL_19;
    v11 = TokenHandlea;
  }
  ClientInformation = PsmpQueryClientInformation(ProcessHandle, v11);
  if ( ClientInformation >= 0 )
  {
    v32 = 464;
    ClientInformation = PsmGetKeyFromToken(TokenHandlea, v33, &v32, &v29);
    if ( ClientInformation >= 0 )
    {
      if ( a4 )
      {
        ClientInformation = PsmpGetHostIdFromProcessToken(TokenHandlea, &v28);
        if ( ClientInformation < 0 )
          goto LABEL_19;
        v8 = v28;
      }
      v13 = v34;
      if ( (v29 & 1) != 0 )
      {
        v13 = v34 | 1;
        v34 |= 1u;
      }
      if ( (v29 & 2) != 0 )
        v34 = v13 | 2;
      v26 = 0;
      v28 = 0;
      v30 = 0;
      ClientInformation = AppModelPolicy_GetPolicy_Internal(
                            (_DWORD)TokenHandlea,
                            v12,
                            (unsigned int)&v26,
                            (unsigned int)&v30,
                            (__int64)&v28);
      if ( ClientInformation >= 0 )
      {
        v14 = 4;
        v33[532] = v26 != 65537 ? 4 : 0;
        v15 = v31;
        do
        {
          v16 = v15[1];
          *a3 = *v15;
          v17 = v15[2];
          a3[1] = v16;
          v18 = v15[3];
          a3[2] = v17;
          v19 = v15[4];
          a3[3] = v18;
          v20 = v15[5];
          a3[4] = v19;
          v21 = v15[6];
          a3[5] = v20;
          v22 = v15[7];
          v15 += 8;
          a3[6] = v21;
          a3[7] = v22;
          a3 += 8;
          --v14;
        }
        while ( v14 );
        v23 = v15[1];
        *a3 = *v15;
        a3[1] = v23;
        if ( a4 )
          *a4 = v8;
        goto LABEL_22;
      }
    }
  }
LABEL_19:
  if ( (unsigned int)dword_18003F080 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003F080, 3, v10) )
  {
    v26 = ClientInformation;
    v36 = &v26;
    v37 = 4;
    ProcessId = GetProcessId(ProcessHandle);
    v39 = 4;
    LODWORD(v28) = ProcessId;
    v38 = &v28;
    tlgWriteTransfer_EventWriteTransfer(&dword_18003F080, &byte_18003851F, 0, 0, 4, v35);
  }
LABEL_22:
  if ( !TokenHandle && TokenHandlea )
    NtClose(TokenHandlea);
  return (unsigned int)ClientInformation;
}

```

## disassembly

```asm
0x180003ec8  push    rbp
0x180003eca  push    rbx
0x180003ecb  push    rsi
0x180003ecc  push    rdi
0x180003ecd  push    r12
0x180003ecf  push    r13
0x180003ed1  push    r14
0x180003ed3  push    r15
0x180003ed5  lea     rbp, [rsp-1D8h]
0x180003edd  sub     rsp, 2D8h
0x180003ee4  mov     rax, cs:__security_cookie
0x180003eeb  xor     rax, rsp
0x180003eee  mov     [rbp+210h+var_50], rax
0x180003ef5  mov     rsi, r8
0x180003ef8  mov     r12, rdx
0x180003efb  mov     r13, rcx
0x180003efe  xor     edx, edx; Val
0x180003f00  mov     r8d, 220h; Size
0x180003f06  lea     rcx, [rsp+310h+var_2B0]; void *
0x180003f0b  mov     r14, r9
0x180003f0e  call    memset_0
0x180003f13  xor     edi, edi
0x180003f15  or      r15, 0FFFFFFFFFFFFFFFFh
0x180003f19  mov     [rsp+310h+TokenHandle], rdi
0x180003f1e  mov     [rsp+310h+var_2D0], r15
0x180003f23  mov     [rsp+310h+var_2C8], rdi
0x180003f28  test    r12, r12
0x180003f2b  jnz     short loc_180003F52
0x180003f2d  lea     r9, [rsp+310h+TokenHandle]; TokenHandle
0x180003f32  xor     r8d, r8d; HandleAttributes
0x180003f35  lea     edx, [rdi+8]; DesiredAccess
0x180003f38  mov     rcx, r13; ProcessHandle
0x180003f3b  call    cs:__imp_NtOpenProcessTokenEx
0x180003f41  mov     ebx, eax
0x180003f43  test    eax, eax
0x180003f45  js      loc_1800040AD
0x180003f4b  mov     rdx, [rsp+310h+TokenHandle]
0x180003f50  jmp     short loc_180003F5A
0x180003f52  mov     rdx, r12; TokenHandle
0x180003f55  mov     [rsp+310h+TokenHandle], rdx
0x180003f5a  lea     r9, [rbp+210h+var_D8]
0x180003f61  mov     rcx, r13; ProcessHandle
0x180003f64  lea     r8, [rsp+310h+var_2B0]
0x180003f69  call    PsmpQueryClientInformation
0x180003f6e  mov     ebx, eax
0x180003f70  test    eax, eax
0x180003f72  js      loc_1800040AD
0x180003f78  mov     rcx, [rsp+310h+TokenHandle]
0x180003f7d  lea     r9, [rsp+310h+var_2C8]
0x180003f82  lea     r8, [rsp+310h+var_2AC]
0x180003f87  mov     [rsp+310h+var_2AC], 1D0h
0x180003f8f  lea     rdx, [rsp+310h+var_2A8]
0x180003f94  call    cs:__imp_PsmGetKeyFromToken
0x180003f9a  mov     ebx, eax
0x180003f9c  test    eax, eax
0x180003f9e  js      loc_1800040AD
0x180003fa4  test    r14, r14
0x180003fa7  jz      short loc_180003FC7
0x180003fa9  mov     rcx, [rsp+310h+TokenHandle]
0x180003fae  lea     rdx, [rsp+310h+var_2D0]
0x180003fb3  call    PsmpGetHostIdFromProcessToken
0x180003fb8  mov     ebx, eax
0x180003fba  test    eax, eax
0x180003fbc  js      loc_1800040AD
0x180003fc2  mov     r15, [rsp+310h+var_2D0]
0x180003fc7  test    byte ptr [rsp+310h+var_2C8], 1
0x180003fcc  mov     al, [rbp+210h+var_93]
0x180003fd2  jz      short loc_180003FDC
0x180003fd4  or      al, 1
0x180003fd6  mov     [rbp+210h+var_93], al
0x180003fdc  test    byte ptr [rsp+310h+var_2C8], 2
0x180003fe1  jz      short loc_180003FEB
0x180003fe3  or      al, 2
0x180003fe5  mov     [rbp+210h+var_93], al
0x180003feb  mov     rcx, [rsp+310h+TokenHandle]
0x180003ff0  lea     rax, [rsp+310h+var_2D0]
0x180003ff5  lea     r9, [rsp+310h+var_2C0]
0x180003ffa  mov     [rsp+310h+var_2F0], rax
0x180003fff  lea     r8, [rsp+310h+var_2E0]
0x180004004  mov     [rsp+310h+var_2E0], edi
0x180004008  mov     [rsp+310h+var_2D0], rdi
0x18000400d  mov     [rsp+310h+var_2C0], rdi
0x180004012  call    AppModelPolicy_GetPolicy_Internal
0x180004017  mov     ebx, eax
0x180004019  test    eax, eax
0x18000401b  js      loc_1800040AD
0x180004021  mov     eax, [rsp+310h+var_2E0]
0x180004025  mov     edi, 4
0x18000402a  sub     eax, 10001h
0x18000402f  neg     eax
0x180004031  sbb     al, al
0x180004033  lea     ecx, [rdi+7Ch]
0x180004036  and     al, dil
0x180004039  mov     [rbp+210h+var_94], al
0x18000403f  lea     rax, [rsp+310h+var_2B0]
0x180004044  movups  xmm0, xmmword ptr [rax]
0x180004047  movups  xmm1, xmmword ptr [rax+10h]
0x18000404b  movups  xmmword ptr [rsi], xmm0
0x18000404e  movups  xmm0, xmmword ptr [rax+20h]
0x180004052  movups  xmmword ptr [rsi+10h], xmm1
0x180004056  movups  xmm1, xmmword ptr [rax+30h]
0x18000405a  movups  xmmword ptr [rsi+20h], xmm0
0x18000405e  movups  xmm0, xmmword ptr [rax+40h]
0x180004062  movups  xmmword ptr [rsi+30h], xmm1
0x180004066  movups  xmm1, xmmword ptr [rax+50h]
0x18000406a  movups  xmmword ptr [rsi+40h], xmm0
0x18000406e  movups  xmm0, xmmword ptr [rax+60h]
0x180004072  movups  xmmword ptr [rsi+50h], xmm1
0x180004076  movups  xmm1, xmmword ptr [rax+70h]
0x18000407a  add     rax, rcx
0x18000407d  movups  xmmword ptr [rsi+60h], xmm0
0x180004081  movups  xmmword ptr [rsi+70h], xmm1
0x180004085  add     rsi, rcx
0x180004088  sub     rdi, 1
0x18000408c  jnz     short loc_180004044
0x18000408e  movups  xmm0, xmmword ptr [rax]
0x180004091  movups  xmm1, xmmword ptr [rax+10h]
0x180004095  movups  xmmword ptr [rsi], xmm0
0x180004098  movups  xmmword ptr [rsi+10h], xmm1
0x18000409c  test    r14, r14
0x18000409f  jz      loc_18000412F
0x1800040a5  mov     [r14], r15
0x1800040a8  jmp     loc_18000412F
0x1800040ad  mov     eax, cs:dword_18003F080
0x1800040b3  mov     edi, 4
0x1800040b8  cmp     eax, edi
0x1800040ba  jbe     short loc_18000412F
0x1800040bc  lea     edx, [rdi-1]
0x1800040bf  lea     rcx, dword_18003F080
0x1800040c6  call    _tlgKeywordOn
0x1800040cb  test    al, al
0x1800040cd  jz      short loc_18000412F
0x1800040cf  lea     rax, [rsp+310h+var_2E0]
0x1800040d4  mov     [rsp+310h+var_2E0], ebx
0x1800040d8  mov     rcx, r13; Process
0x1800040db  mov     [rbp+210h+var_70], rax
0x1800040e2  mov     [rbp+210h+var_68], rdi
0x1800040e9  call    cs:__imp_GetProcessId
0x1800040ef  xor     r9d, r9d
0x1800040f2  mov     [rbp+210h+var_58], rdi
0x1800040f9  mov     dword ptr [rsp+310h+var_2D0], eax
0x1800040fd  lea     rdx, byte_18003851F
0x180004104  lea     rax, [rsp+310h+var_2D0]
0x180004109  xor     r8d, r8d
0x18000410c  mov     [rbp+210h+var_60], rax
0x180004113  lea     rcx, dword_18003F080
0x18000411a  lea     rax, [rbp+210h+var_90]
0x180004121  mov     [rsp+310h+var_2E8], rax
0x180004126  mov     dword ptr [rsp+310h+var_2F0], edi
0x18000412a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000412f  test    r12, r12
0x180004132  jnz     short loc_180004144
0x180004134  mov     rcx, [rsp+310h+TokenHandle]; Handle
0x180004139  test    rcx, rcx
0x18000413c  jz      short loc_180004144
0x18000413e  call    cs:__imp_NtClose
0x180004144  mov     eax, ebx
0x180004146  mov     rcx, [rbp+210h+var_50]
0x18000414d  xor     rcx, rsp; StackCookie
0x180004150  call    __security_check_cookie
0x180004155  add     rsp, 2D8h
0x18000415c  pop     r15
0x18000415e  pop     r14
0x180004160  pop     r13
0x180004162  pop     r12
0x180004164  pop     rdi
0x180004165  pop     rsi
0x180004166  pop     rbx
0x180004167  pop     rbp
0x180004168  retn
```
