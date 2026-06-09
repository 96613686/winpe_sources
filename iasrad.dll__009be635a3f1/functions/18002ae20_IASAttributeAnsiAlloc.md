# IASAttributeAnsiAlloc

- ea: `0x18002ae20`
- end: `0x18002aefc`
- name: `IASAttributeAnsiAlloc`
- size: `220`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013458`
- `0x1800186b8`
- `0x18001b3f0`
- `0x18002569c`

## callees

- `0x18002ae20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002ae92`
- `KERNEL32!GetLastError` at `0x18002ae92`
- `KERNEL32!WideCharToMultiByte` at `0x18002ae85`
- `KERNEL32!WideCharToMultiByte` at `0x18002aed7`
- `KERNEL32!WideCharToMultiByte` at `0x18002ae85`
- `KERNEL32!WideCharToMultiByte` at `0x18002aed7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aee4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aee4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ae9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ae9d`

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
0x18002ae20  mov     rax, rsp
0x18002ae23  mov     [rax+8], rbx
0x18002ae27  mov     [rax+10h], rsi
0x18002ae2b  push    rdi
0x18002ae2c  sub     rsp, 40h
0x18002ae30  mov     rbx, rcx
0x18002ae33  test    rcx, rcx
0x18002ae36  jz      loc_18002AEEA
0x18002ae3c  cmp     dword ptr [rcx+10h], 5
0x18002ae40  jnz     loc_18002AEEA
0x18002ae46  cmp     qword ptr [rcx+18h], 0
0x18002ae4b  jnz     loc_18002AEEA
0x18002ae51  mov     r8, [rcx+20h]; lpWideCharStr
0x18002ae55  test    r8, r8
0x18002ae58  jz      loc_18002AEEA
0x18002ae5e  mov     qword ptr [rax-10h], 0
0x18002ae66  or      r9d, 0FFFFFFFFh; cchWideChar
0x18002ae6a  mov     qword ptr [rax-18h], 0
0x18002ae72  xor     edx, edx; dwFlags
0x18002ae74  mov     dword ptr [rax-20h], 0
0x18002ae7b  xor     ecx, ecx; CodePage
0x18002ae7d  mov     qword ptr [rax-28h], 0
0x18002ae85  call    cs:__imp_WideCharToMultiByte
0x18002ae8b  movsxd  rsi, eax
0x18002ae8e  test    eax, eax
0x18002ae90  jnz     short loc_18002AE9A
0x18002ae92  call    cs:__imp_GetLastError
0x18002ae98  jmp     short loc_18002AEEC
0x18002ae9a  mov     rcx, rsi; cb
0x18002ae9d  call    cs:__imp_CoTaskMemAlloc
0x18002aea3  mov     rdi, rax
0x18002aea6  test    rax, rax
0x18002aea9  jnz     short loc_18002AEB0
0x18002aeab  lea     eax, [rdi+8]
0x18002aeae  jmp     short loc_18002AEEC
0x18002aeb0  mov     r8, [rbx+20h]; lpWideCharStr
0x18002aeb4  or      r9d, 0FFFFFFFFh; cchWideChar
0x18002aeb8  mov     [rsp+48h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18002aec1  xor     edx, edx; dwFlags
0x18002aec3  mov     [rsp+48h+lpDefaultChar], 0; lpDefaultChar
0x18002aecc  xor     ecx, ecx; CodePage
0x18002aece  mov     [rsp+48h+cbMultiByte], esi; cbMultiByte
0x18002aed2  mov     [rsp+48h+lpMultiByteStr], rdi; lpMultiByteStr
0x18002aed7  call    cs:__imp_WideCharToMultiByte
0x18002aedd  xchg    rdi, [rbx+18h]
0x18002aee1  mov     rcx, rdi; pv
0x18002aee4  call    cs:__imp_CoTaskMemFree
0x18002aeea  xor     eax, eax
0x18002aeec  mov     rbx, [rsp+48h+arg_0]
0x18002aef1  mov     rsi, [rsp+48h+arg_8]
0x18002aef6  add     rsp, 40h
0x18002aefa  pop     rdi
0x18002aefb  retn
```
