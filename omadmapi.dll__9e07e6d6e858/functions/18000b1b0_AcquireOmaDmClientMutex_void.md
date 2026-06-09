# AcquireOmaDmClientMutex(void * *)

- ea: `0x18000b1b0`
- end: `0x18000b263`
- name: `?AcquireOmaDmClientMutex@@YAJPEAPEAX@Z`
- size: `179`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007930`
- `0x18000b1b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b1dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b224`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b1fe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000b1fe`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000b1c8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000b1c8`

## pseudocode

```c
signed int __fastcall AcquireOmaDmClientMutex(void **a1)
{
  HANDLE MutexW; // rax
  void *v3; // rbx
  signed int result; // eax
  DWORD v5; // eax
  unsigned int v6; // edi
  signed int LastError; // eax

  MutexW = CreateMutexW(0, 0, L"__OMADMCLIENT_NAMED_MUTEX__");
  v3 = MutexW;
  if ( MutexW )
  {
    v5 = WaitForSingleObject(MutexW, 0xEA60u);
    if ( (v5 & 0xFFFFFF7F) != 0 )
    {
      if ( v5 == 258 )
      {
        v6 = -2147023436;
      }
      else if ( v5 == -1 )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v6 = -2147418113;
      }
      ReleaseOmaDmMutex(v3);
      return v6;
    }
    else
    {
      *a1 = v3;
      return 0;
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000b1b0  mov     [rsp+arg_0], rbx
0x18000b1b5  push    rdi
0x18000b1b6  sub     rsp, 20h
0x18000b1ba  mov     rdi, rcx
0x18000b1bd  lea     r8, aOmadmclientNam; "__OMADMCLIENT_NAMED_MUTEX__"
0x18000b1c4  xor     ecx, ecx; lpMutexAttributes
0x18000b1c6  xor     edx, edx; bInitialOwner
0x18000b1c8  call    cs:__imp_CreateMutexW
0x18000b1cf  nop     dword ptr [rax+rax+00h]
0x18000b1d4  mov     rbx, rax
0x18000b1d7  test    rax, rax
0x18000b1da  jnz     short loc_18000B1F6
0x18000b1dc  call    cs:__imp_GetLastError
0x18000b1e3  nop     dword ptr [rax+rax+00h]
0x18000b1e8  test    eax, eax
0x18000b1ea  jle     short loc_18000B257
0x18000b1ec  movzx   eax, ax
0x18000b1ef  or      eax, 80070000h
0x18000b1f4  jmp     short loc_18000B257
0x18000b1f6  mov     edx, 0EA60h; dwMilliseconds
0x18000b1fb  mov     rcx, rbx; hHandle
0x18000b1fe  call    cs:__imp_WaitForSingleObject
0x18000b205  nop     dword ptr [rax+rax+00h]
0x18000b20a  test    eax, 0FFFFFF7Fh
0x18000b20f  jz      short loc_18000B252
0x18000b211  cmp     eax, 102h
0x18000b216  jz      short loc_18000B241
0x18000b218  cmp     eax, 0FFFFFFFFh
0x18000b21b  jz      short loc_18000B224
0x18000b21d  mov     edi, 8000FFFFh
0x18000b222  jmp     short loc_18000B246
0x18000b224  call    cs:__imp_GetLastError
0x18000b22b  nop     dword ptr [rax+rax+00h]
0x18000b230  mov     edi, eax
0x18000b232  test    eax, eax
0x18000b234  jle     short loc_18000B246
0x18000b236  movzx   edi, ax
0x18000b239  or      edi, 80070000h
0x18000b23f  jmp     short loc_18000B246
0x18000b241  mov     edi, 800705B4h
0x18000b246  mov     rcx, rbx; hObject
0x18000b249  call    ?ReleaseOmaDmMutex@@YAXPEAX@Z; ReleaseOmaDmMutex(void *)
0x18000b24e  mov     eax, edi
0x18000b250  jmp     short loc_18000B257
0x18000b252  mov     [rdi], rbx
0x18000b255  xor     eax, eax
0x18000b257  mov     rbx, [rsp+28h+arg_0]
0x18000b25c  add     rsp, 20h
0x18000b260  pop     rdi
0x18000b261  retn
```
