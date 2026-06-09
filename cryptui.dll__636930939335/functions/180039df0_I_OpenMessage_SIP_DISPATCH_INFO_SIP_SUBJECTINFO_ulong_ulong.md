# I_OpenMessage(SIP_DISPATCH_INFO_ *,SIP_SUBJECTINFO_ *,ulong *,ulong)

- ea: `0x180039df0`
- end: `0x180039f40`
- name: `?I_OpenMessage@@YAPEAXPEAUSIP_DISPATCH_INFO_@@PEAUSIP_SUBJECTINFO_@@PEAKK@Z`
- size: `336`
- prototype: `void *__fastcall(struct SIP_DISPATCH_INFO_ *, struct SIP_SUBJECTINFO_ *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180039c10`

## callees

- `0x180039d5c`
- `0x180039df0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039e43`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039e5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039efe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039e5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039efe`
- `CRYPT32!CryptMsgGetParam` at `0x180039ee4`
- `CRYPT32!CryptMsgGetParam` at `0x180039ee4`
- `CRYPT32!CryptMsgClose` at `0x180039f24`
- `CRYPT32!CryptMsgClose` at `0x180039f24`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039e78`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039e78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039f12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039f12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039e6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039f04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039e6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039f04`

## pseudocode

```c
void *__fastcall I_OpenMessage(struct SIP_DISPATCH_INFO_ *a1, struct SIP_SUBJECTINFO_ *a2, unsigned int *a3)
{
  void *v4; // rdi
  DWORD LastError; // eax
  DWORD v8; // ecx
  SIZE_T v9; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int8 *v11; // rsi
  int Param; // ebx
  HANDLE v13; // rax
  DWORD pcbData[14]; // [rsp+30h] [rbp-38h] BYREF
  int pvData; // [rsp+70h] [rbp+8h] BYREF
  SIZE_T dwBytes; // [rsp+88h] [rbp+20h] BYREF

  pcbData[0] = 4;
  v4 = 0;
  LODWORD(dwBytes) = 0;
  pvData = 0;
  ((void (__fastcall *)(struct SIP_SUBJECTINFO_ *, unsigned int *, _QWORD, SIZE_T *, _QWORD))a1->pfGet)(
    a2,
    a3,
    0,
    &dwBytes,
    0);
  if ( (_DWORD)dwBytes )
  {
    v9 = (unsigned int)dwBytes;
    ProcessHeap = GetProcessHeap();
    v11 = (unsigned __int8 *)HeapAlloc(ProcessHeap, 0, v9);
    if ( !v11 )
    {
      v8 = 14;
      goto LABEL_5;
    }
    Param = ((__int64 (__fastcall *)(struct SIP_SUBJECTINFO_ *, unsigned int *, _QWORD, SIZE_T *, unsigned __int8 *))a1->pfGet)(
              a2,
              a3,
              0,
              &dwBytes,
              v11);
    if ( Param )
    {
      v4 = I_OpenBlob(*a3, v11, dwBytes);
      if ( v4 )
      {
        Param = CryptMsgGetParam(v4, 5u, 0, &pvData, pcbData);
        if ( Param )
        {
          if ( !pvData )
          {
            Param = 0;
            SetLastError(0x800B0100);
          }
        }
      }
    }
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v11);
    if ( !Param && v4 )
    {
      CryptMsgClose(v4);
      return 0;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 11 || LastError == 87 )
    {
      v8 = -2146762496;
LABEL_5:
      SetLastError(v8);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180039df0  mov     rax, rsp
0x180039df3  mov     [rax+10h], rbx
0x180039df7  mov     [rax+20h], r9d
0x180039dfb  push    rbp
0x180039dfc  push    rsi
0x180039dfd  push    rdi
0x180039dfe  push    r14
0x180039e00  push    r15
0x180039e02  sub     rsp, 40h
0x180039e06  mov     r15, rcx
0x180039e09  mov     dword ptr [rax-38h], 4
0x180039e10  xor     edi, edi
0x180039e12  lea     r9, [rax+20h]
0x180039e16  mov     r14, r8
0x180039e19  mov     [rax+20h], edi
0x180039e1c  mov     rbp, rdx
0x180039e1f  mov     [rax+8], edi
0x180039e22  mov     [rax-48h], rdi
0x180039e26  xor     r8d, r8d
0x180039e29  mov     rax, [r15+10h]
0x180039e2d  mov     rdx, r14
0x180039e30  mov     rcx, rbp
0x180039e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e38  mov     eax, dword ptr [rsp+68h+dwBytes]
0x180039e3f  test    eax, eax
0x180039e41  jnz     short loc_180039E67
0x180039e43  call    cs:__imp_GetLastError
0x180039e49  cmp     eax, 0Bh
0x180039e4c  jz      short loc_180039E57
0x180039e4e  cmp     eax, 57h ; 'W'
0x180039e51  jnz     loc_180039F2C
0x180039e57  mov     ecx, 800B0100h; dwErrCode
0x180039e5c  call    cs:__imp_SetLastError
0x180039e62  jmp     loc_180039F2C
0x180039e67  mov     rbx, rax
0x180039e6a  call    cs:__imp_GetProcessHeap
0x180039e70  mov     r8, rbx; dwBytes
0x180039e73  xor     edx, edx; dwFlags
0x180039e75  mov     rcx, rax; hHeap
0x180039e78  call    cs:__imp_HeapAlloc
0x180039e7e  mov     rsi, rax
0x180039e81  test    rax, rax
0x180039e84  jnz     short loc_180039E8B
0x180039e86  lea     ecx, [rax+0Eh]
0x180039e89  jmp     short loc_180039E5C
0x180039e8b  mov     rax, [r15+10h]
0x180039e8f  lea     r9, [rsp+68h+dwBytes]
0x180039e97  xor     r8d, r8d
0x180039e9a  mov     [rsp+68h+pcbData], rsi
0x180039e9f  mov     rdx, r14
0x180039ea2  mov     rcx, rbp
0x180039ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039eaa  mov     ebx, eax
0x180039eac  test    eax, eax
0x180039eae  jz      short loc_180039F04
0x180039eb0  mov     r8d, dword ptr [rsp+68h+dwBytes]; unsigned int
0x180039eb8  mov     rdx, rsi; unsigned __int8 *
0x180039ebb  mov     ecx, [r14]; unsigned int
0x180039ebe  call    ?I_OpenBlob@@YAPEAXKPEAEK@Z; I_OpenBlob(ulong,uchar *,ulong)
0x180039ec3  mov     rdi, rax
0x180039ec6  test    rax, rax
0x180039ec9  jz      short loc_180039F04
0x180039ecb  xor     r8d, r8d; dwIndex
0x180039ece  lea     rax, [rsp+68h+var_38]
0x180039ed3  lea     r9, [rsp+68h+pvData]; pvData
0x180039ed8  mov     [rsp+68h+pcbData], rax; pcbData
0x180039edd  mov     rcx, rdi; hCryptMsg
0x180039ee0  lea     edx, [r8+5]; dwParamType
0x180039ee4  call    cs:__imp_CryptMsgGetParam
0x180039eea  mov     ebx, eax
0x180039eec  test    eax, eax
0x180039eee  jz      short loc_180039F04
0x180039ef0  cmp     [rsp+68h+pvData], 0
0x180039ef5  jnz     short loc_180039F04
0x180039ef7  xor     ebx, ebx
0x180039ef9  mov     ecx, 800B0100h; dwErrCode
0x180039efe  call    cs:__imp_SetLastError
0x180039f04  call    cs:__imp_GetProcessHeap
0x180039f0a  mov     r8, rsi; lpMem
0x180039f0d  xor     edx, edx; dwFlags
0x180039f0f  mov     rcx, rax; hHeap
0x180039f12  call    cs:__imp_HeapFree
0x180039f18  test    ebx, ebx
0x180039f1a  jnz     short loc_180039F2C
0x180039f1c  test    rdi, rdi
0x180039f1f  jz      short loc_180039F2C
0x180039f21  mov     rcx, rdi; hCryptMsg
0x180039f24  call    cs:__imp_CryptMsgClose
0x180039f2a  xor     edi, edi
0x180039f2c  mov     rbx, [rsp+68h+arg_8]
0x180039f31  mov     rax, rdi
0x180039f34  add     rsp, 40h
0x180039f38  pop     r15
0x180039f3a  pop     r14
0x180039f3c  pop     rdi
0x180039f3d  pop     rsi
0x180039f3e  pop     rbp
0x180039f3f  retn
```
