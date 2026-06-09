# LogInfoEventString

- ea: `0x180004604`
- end: `0x180004696`
- name: `LogInfoEventString`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004720`

## callees

- `0x180004604`
- `0x180011ba0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x18000467e`
- `ADVAPI32!EventWrite` at `0x18000467e`

## pseudocode

```c
void __fastcall LogInfoEventString(__int64 a1, const wchar_t *a2)
{
  __int64 v2; // rax
  ULONG v3; // eax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-28h] BYREF

  if ( g_hEventProviderHandle && *(int *)&g_dwLoggingLevel >= 2 )
  {
    if ( a2 )
    {
      v2 = -1;
      do
        ++v2;
      while ( a2[v2] );
      v3 = 2 * v2 + 2;
    }
    else
    {
      v3 = 10;
    }
    UserData.Reserved = 0;
    UserData.Size = v3;
    if ( !a2 )
      a2 = L"NULL";
    UserData.Ptr = (ULONGLONG)a2;
    EventWrite(g_hEventProviderHandle, &EVENT_INFO_NO_PORTMAPPER, 1u, &UserData);
  }
}

```

## disassembly

```asm
0x180004604  sub     rsp, 48h
0x180004608  mov     rax, cs:__security_cookie
0x18000460f  xor     rax, rsp
0x180004612  mov     [rsp+48h+var_18], rax
0x180004617  mov     rcx, cs:g_hEventProviderHandle; RegHandle
0x18000461e  xor     r9d, r9d
0x180004621  test    rcx, rcx
0x180004624  jz      short loc_180004684
0x180004626  cmp     cs:g_dwLoggingLevel, 2
0x18000462d  jl      short loc_180004684
0x18000462f  test    rdx, rdx
0x180004632  jz      short loc_18000464B
0x180004634  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004638  inc     rax
0x18000463b  cmp     [rdx+rax*2], r9w
0x180004640  jnz     short loc_180004638
0x180004642  lea     eax, ds:2[rax*2]
0x180004649  jmp     short loc_180004650
0x18000464b  mov     eax, 0Ah
0x180004650  test    rdx, rdx
0x180004653  mov     dword ptr [rsp+48h+UserData.0Ch], r9d
0x180004658  lea     r8, aNull_0; "NULL"
0x18000465f  mov     [rsp+48h+UserData.Size], eax
0x180004663  cmovz   rdx, r8
0x180004667  lea     r9, [rsp+48h+UserData]; UserData
0x18000466c  mov     [rsp+48h+UserData.Ptr], rdx
0x180004671  mov     r8d, 1; UserDataCount
0x180004677  lea     rdx, EVENT_INFO_NO_PORTMAPPER; EventDescriptor
0x18000467e  call    cs:__imp_EventWrite
0x180004684  mov     rcx, [rsp+48h+var_18]
0x180004689  xor     rcx, rsp; StackCookie
0x18000468c  call    __security_check_cookie
0x180004691  add     rsp, 48h
0x180004695  retn
```
