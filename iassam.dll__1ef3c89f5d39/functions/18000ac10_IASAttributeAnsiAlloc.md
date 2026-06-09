# IASAttributeAnsiAlloc

- ea: `0x18000ac10`
- end: `0x18000acec`
- name: `IASAttributeAnsiAlloc`
- size: `220`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015b88`
- `0x18001be30`

## callees

- `0x18000ac10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ac82`
- `KERNEL32!GetLastError` at `0x18000ac82`
- `KERNEL32!WideCharToMultiByte` at `0x18000ac75`
- `KERNEL32!WideCharToMultiByte` at `0x18000acc7`
- `KERNEL32!WideCharToMultiByte` at `0x18000ac75`
- `KERNEL32!WideCharToMultiByte` at `0x18000acc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ac8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ac8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000acd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000acd4`

## pseudocode

```c
DWORD __fastcall IASAttributeAnsiAlloc(__int64 a1)
{
  const WCHAR *v2; // r8
  int v3; // eax
  int cbMultiByte; // esi
  CHAR *lpMultiByteStr; // rax
  __int64 v7; // rdi

  if ( a1 )
  {
    if ( *(_DWORD *)(a1 + 16) == 5 && !*(_QWORD *)(a1 + 24) )
    {
      v2 = *(const WCHAR **)(a1 + 32);
      if ( v2 )
      {
        v3 = WideCharToMultiByte(0, 0, v2, -1, 0, 0, 0, 0);
        cbMultiByte = v3;
        if ( !v3 )
          return GetLastError();
        lpMultiByteStr = (CHAR *)CoTaskMemAlloc(v3);
        v7 = (__int64)lpMultiByteStr;
        if ( !lpMultiByteStr )
          return 8;
        WideCharToMultiByte(0, 0, *(LPCWCH *)(a1 + 32), -1, lpMultiByteStr, cbMultiByte, 0, 0);
        CoTaskMemFree((LPVOID)_InterlockedExchange64((volatile __int64 *)(a1 + 24), v7));
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000ac10  mov     rax, rsp
0x18000ac13  mov     [rax+8], rbx
0x18000ac17  mov     [rax+10h], rsi
0x18000ac1b  push    rdi
0x18000ac1c  sub     rsp, 40h
0x18000ac20  mov     rbx, rcx
0x18000ac23  test    rcx, rcx
0x18000ac26  jz      loc_18000ACDA
0x18000ac2c  cmp     dword ptr [rcx+10h], 5
0x18000ac30  jnz     loc_18000ACDA
0x18000ac36  cmp     qword ptr [rcx+18h], 0
0x18000ac3b  jnz     loc_18000ACDA
0x18000ac41  mov     r8, [rcx+20h]; lpWideCharStr
0x18000ac45  test    r8, r8
0x18000ac48  jz      loc_18000ACDA
0x18000ac4e  mov     qword ptr [rax-10h], 0
0x18000ac56  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000ac5a  mov     qword ptr [rax-18h], 0
0x18000ac62  xor     edx, edx; dwFlags
0x18000ac64  mov     dword ptr [rax-20h], 0
0x18000ac6b  xor     ecx, ecx; CodePage
0x18000ac6d  mov     qword ptr [rax-28h], 0
0x18000ac75  call    cs:__imp_WideCharToMultiByte
0x18000ac7b  movsxd  rsi, eax
0x18000ac7e  test    eax, eax
0x18000ac80  jnz     short loc_18000AC8A
0x18000ac82  call    cs:__imp_GetLastError
0x18000ac88  jmp     short loc_18000ACDC
0x18000ac8a  mov     rcx, rsi; cb
0x18000ac8d  call    cs:__imp_CoTaskMemAlloc
0x18000ac93  mov     rdi, rax
0x18000ac96  test    rax, rax
0x18000ac99  jnz     short loc_18000ACA0
0x18000ac9b  lea     eax, [rdi+8]
0x18000ac9e  jmp     short loc_18000ACDC
0x18000aca0  mov     r8, [rbx+20h]; lpWideCharStr
0x18000aca4  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000aca8  mov     [rsp+48h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18000acb1  xor     edx, edx; dwFlags
0x18000acb3  mov     [rsp+48h+lpDefaultChar], 0; lpDefaultChar
0x18000acbc  xor     ecx, ecx; CodePage
0x18000acbe  mov     [rsp+48h+cbMultiByte], esi; cbMultiByte
0x18000acc2  mov     [rsp+48h+lpMultiByteStr], rdi; lpMultiByteStr
0x18000acc7  call    cs:__imp_WideCharToMultiByte
0x18000accd  xchg    rdi, [rbx+18h]
0x18000acd1  mov     rcx, rdi; pv
0x18000acd4  call    cs:__imp_CoTaskMemFree
0x18000acda  xor     eax, eax
0x18000acdc  mov     rbx, [rsp+48h+arg_0]
0x18000ace1  mov     rsi, [rsp+48h+arg_8]
0x18000ace6  add     rsp, 40h
0x18000acea  pop     rdi
0x18000aceb  retn
```
