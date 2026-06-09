# CreateOrOpenPFsRegistryComponent

- ea: `0x18002bb5c`
- end: `0x18002bcfa`
- name: `CreateOrOpenPFsRegistryComponent`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002be68`

## callees

- `0x180001da6`
- `0x18002bb5c`
- `0x18002bd00`
- `0x18002c964`
- `0x18002ccf4`
- `0x18002d258`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002bcd9`
- `KERNEL32!HeapFree` at `0x18002bcd9`
- `KERNEL32!HeapAlloc` at `0x18002bba8`
- `KERNEL32!HeapAlloc` at `0x18002bba8`
- `KERNEL32!GetProcessHeap` at `0x18002bb94`
- `KERNEL32!GetProcessHeap` at `0x18002bccb`
- `KERNEL32!GetProcessHeap` at `0x18002bb94`
- `KERNEL32!GetProcessHeap` at `0x18002bccb`
- `ADVAPI32!RegCreateKeyExW` at `0x18002bc33`
- `ADVAPI32!RegCreateKeyExW` at `0x18002bc33`
- `CLUSAPI!ClusterRegCreateKey` at `0x18002bc01`
- `CLUSAPI!ClusterRegCreateKey` at `0x18002bc01`

## pseudocode

```c
__int64 __fastcall CreateOrOpenPFsRegistryComponent(
        HKEY a1,
        HKEY a2,
        const void **a3,
        char a4,
        DWORD dwDisposition,
        HKEY *a6,
        _DWORD *a7,
        char a8,
        BYTE *a9,
        char *a10)
{
  __int64 v10; // rbx
  HANDLE ProcessHeap; // rax
  SIZE_T v16; // r8
  unsigned int PFsIdKeyValue; // ebx
  WCHAR *v18; // rax
  WCHAR *v19; // rsi
  size_t v20; // rbx
  LONG v21; // eax
  __int64 v22; // rdx
  DWORD PFsIdKeyValues; // eax
  __int64 v24; // rdx
  HANDLE v25; // rax
  BOOL lpSecurityAttributes; // [rsp+20h] [rbp-30h]
  HKEY phkResult; // [rsp+90h] [rbp+40h] BYREF

  v10 = *(unsigned __int16 *)a3;
  phkResult = 0;
  dwDisposition = 0;
  ProcessHeap = GetProcessHeap();
  v16 = v10 + 2;
  PFsIdKeyValue = 8;
  v18 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v16);
  v19 = v18;
  if ( v18 )
  {
    v20 = *(unsigned __int16 *)a3;
    memcpy_0(v18, a3[1], v20);
    v19[v20 >> 1] = 0;
    if ( a4 )
      v21 = ClusterRegCreateKey(a2, v19, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
    else
      v21 = RegCreateKeyExW(a2, v19, 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
    PFsIdKeyValue = v21;
    if ( v21 )
      goto LABEL_16;
    if ( (dwDisposition & 1) != 0 )
    {
      LOBYTE(lpSecurityAttributes) = a8;
      PFsIdKeyValues = CreatePFsIdKeyValues(a1, phkResult, a4, a7, lpSecurityAttributes, a9, a10);
    }
    else
    {
      if ( (dwDisposition & 2) == 0 || !a7 )
        goto LABEL_15;
      LOBYTE(v22) = a4;
      PFsIdKeyValue = QueryPFsIdKeyValue(phkResult, v22);
      if ( !a8 )
      {
LABEL_13:
        if ( PFsIdKeyValue )
        {
          LOBYTE(v24) = a4;
          NfsPFsCloseKey(phkResult, v24);
LABEL_16:
          v25 = GetProcessHeap();
          HeapFree(v25, 0, v19);
          return PFsIdKeyValue;
        }
LABEL_15:
        *a6 = phkResult;
        goto LABEL_16;
      }
      LOBYTE(v24) = a4;
      PFsIdKeyValues = SetPFsTerminalNodeKeyValue(phkResult, v24, 1);
    }
    PFsIdKeyValue = PFsIdKeyValues;
    goto LABEL_13;
  }
  return PFsIdKeyValue;
}

```

## disassembly

```asm
0x18002bb5c  mov     [rsp-28h+arg_0], rbx
0x18002bb61  mov     [rsp-28h+arg_8], rsi
0x18002bb66  push    rbp
0x18002bb67  push    rdi
0x18002bb68  push    r12
0x18002bb6a  push    r14
0x18002bb6c  push    r15
0x18002bb6e  mov     rbp, rsp
0x18002bb71  sub     rsp, 50h
0x18002bb75  movzx   ebx, word ptr [r8]
0x18002bb79  mov     dil, r9b
0x18002bb7c  mov     r14, r8
0x18002bb7f  mov     [rbp+arg_10], 0
0x18002bb87  mov     r15, rdx
0x18002bb8a  mov     [rbp+dwDisposition], 0
0x18002bb91  mov     r12, rcx
0x18002bb94  call    cs:__imp_GetProcessHeap
0x18002bb9a  lea     r8, [rbx+2]; dwBytes
0x18002bb9e  mov     ebx, 8
0x18002bba3  mov     edx, ebx; dwFlags
0x18002bba5  mov     rcx, rax; hHeap
0x18002bba8  call    cs:__imp_HeapAlloc
0x18002bbae  mov     rsi, rax
0x18002bbb1  test    rax, rax
0x18002bbb4  jz      loc_18002BCDF
0x18002bbba  movzx   ebx, word ptr [r14]
0x18002bbbe  mov     rcx, rax; void *
0x18002bbc1  mov     rdx, [r14+8]; Src
0x18002bbc5  mov     r8d, ebx; Size
0x18002bbc8  call    memcpy_0
0x18002bbcd  xor     eax, eax
0x18002bbcf  shr     rbx, 1
0x18002bbd2  xor     r8d, r8d; Reserved
0x18002bbd5  mov     rdx, rsi; lpSubKey
0x18002bbd8  mov     rcx, r15; hKey
0x18002bbdb  mov     [rsi+rbx*2], ax
0x18002bbdf  lea     rax, [rbp+dwDisposition]
0x18002bbe3  test    dil, dil
0x18002bbe6  jz      short loc_18002BC09
0x18002bbe8  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x18002bbed  mov     r9d, 0F003Fh; samDesired
0x18002bbf3  lea     rax, [rbp+arg_10]
0x18002bbf7  mov     [rsp+50h+phkResult], rax; phkResult
0x18002bbfc  mov     [rsp+50h+lpSecurityAttributes], r8; lpSecurityAttributes
0x18002bc01  call    cs:__imp_ClusterRegCreateKey
0x18002bc07  jmp     short loc_18002BC39
0x18002bc09  mov     [rsp+50h+var_10], rax; lpdwDisposition
0x18002bc0e  xor     r9d, r9d; lpClass
0x18002bc11  lea     rax, [rbp+arg_10]
0x18002bc15  mov     [rsp+50h+var_18], rax; phkResult
0x18002bc1a  mov     [rsp+50h+lpdwDisposition], 0; lpSecurityAttributes
0x18002bc23  mov     dword ptr [rsp+50h+phkResult], 0F003Fh; samDesired
0x18002bc2b  mov     dword ptr [rsp+50h+lpSecurityAttributes], 0; dwOptions
0x18002bc33  call    cs:__imp_RegCreateKeyExW
0x18002bc39  mov     ebx, eax
0x18002bc3b  test    eax, eax
0x18002bc3d  jnz     loc_18002BCCB
0x18002bc43  test    byte ptr [rbp+dwDisposition], 1
0x18002bc47  jz      short loc_18002BC77
0x18002bc49  mov     rax, [rbp+arg_48]
0x18002bc4d  mov     r8b, dil
0x18002bc50  mov     r9, [rbp+arg_30]
0x18002bc54  mov     rcx, r12
0x18002bc57  mov     rdx, [rbp+arg_10]
0x18002bc5b  mov     [rsp+50h+lpdwDisposition], rax
0x18002bc60  mov     rax, [rbp+arg_40]
0x18002bc64  mov     [rsp+50h+phkResult], rax
0x18002bc69  mov     al, [rbp+arg_38]
0x18002bc6c  mov     byte ptr [rsp+50h+lpSecurityAttributes], al
0x18002bc70  call    CreatePFsIdKeyValues
0x18002bc75  jmp     short loc_18002BCAC
0x18002bc77  test    byte ptr [rbp+dwDisposition], 2
0x18002bc7b  jz      short loc_18002BCC0
0x18002bc7d  mov     r8, [rbp+arg_30]
0x18002bc81  test    r8, r8
0x18002bc84  jz      short loc_18002BCC0
0x18002bc86  mov     rcx, [rbp+arg_10]
0x18002bc8a  mov     dl, dil
0x18002bc8d  call    QueryPFsIdKeyValue
0x18002bc92  cmp     [rbp+arg_38], 0
0x18002bc96  mov     ebx, eax
0x18002bc98  jz      short loc_18002BCAE
0x18002bc9a  mov     rcx, [rbp+arg_10]
0x18002bc9e  mov     r8d, 1
0x18002bca4  mov     dl, dil
0x18002bca7  call    SetPFsTerminalNodeKeyValue
0x18002bcac  mov     ebx, eax
0x18002bcae  test    ebx, ebx
0x18002bcb0  jz      short loc_18002BCC0
0x18002bcb2  mov     rcx, [rbp+arg_10]
0x18002bcb6  mov     dl, dil
0x18002bcb9  call    NfsPFsCloseKey
0x18002bcbe  jmp     short loc_18002BCCB
0x18002bcc0  mov     rcx, [rbp+arg_28]
0x18002bcc4  mov     rax, [rbp+arg_10]
0x18002bcc8  mov     [rcx], rax
0x18002bccb  call    cs:__imp_GetProcessHeap
0x18002bcd1  mov     r8, rsi; lpMem
0x18002bcd4  xor     edx, edx; dwFlags
0x18002bcd6  mov     rcx, rax; hHeap
0x18002bcd9  call    cs:__imp_HeapFree
0x18002bcdf  lea     r11, [rsp+50h+var_s0]
0x18002bce4  mov     eax, ebx
0x18002bce6  mov     rbx, [r11+30h]
0x18002bcea  mov     rsi, [r11+38h]
0x18002bcee  mov     rsp, r11
0x18002bcf1  pop     r15
0x18002bcf3  pop     r14
0x18002bcf5  pop     r12
0x18002bcf7  pop     rdi
0x18002bcf8  pop     rbp
0x18002bcf9  retn
```
