# LogInfoEventString

- ea: `0x180004914`
- end: `0x1800049ad`
- name: `LogInfoEventString`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004a40`

## callees

- `0x180004914`
- `0x180012e70`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x18000498e`
- `ADVAPI32!EventWrite` at `0x18000498e`

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
0x180004914  sub     rsp, 48h
0x180004918  mov     rax, cs:__security_cookie
0x18000491f  xor     rax, rsp
0x180004922  mov     [rsp+48h+var_18], rax
0x180004927  mov     rcx, cs:g_hEventProviderHandle; RegHandle
0x18000492e  xor     r9d, r9d
0x180004931  test    rcx, rcx
0x180004934  jz      short loc_18000499A
0x180004936  cmp     cs:g_dwLoggingLevel, 2
0x18000493d  jl      short loc_18000499A
0x18000493f  test    rdx, rdx
0x180004942  jz      short loc_18000495B
0x180004944  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004948  inc     rax
0x18000494b  cmp     [rdx+rax*2], r9w
0x180004950  jnz     short loc_180004948
0x180004952  lea     eax, ds:2[rax*2]
0x180004959  jmp     short loc_180004960
0x18000495b  mov     eax, 0Ah
0x180004960  test    rdx, rdx
0x180004963  mov     dword ptr [rsp+48h+UserData.0Ch], r9d
0x180004968  lea     r8, aNull_0; "NULL"
0x18000496f  mov     [rsp+48h+UserData.Size], eax
0x180004973  cmovz   rdx, r8
0x180004977  lea     r9, [rsp+48h+UserData]; UserData
0x18000497c  mov     [rsp+48h+UserData.Ptr], rdx
0x180004981  mov     r8d, 1; UserDataCount
0x180004987  lea     rdx, EVENT_INFO_NO_PORTMAPPER; EventDescriptor
0x18000498e  call    cs:__imp_EventWrite
0x180004995  nop     dword ptr [rax+rax+00h]
0x18000499a  mov     rcx, [rsp+48h+var_18]
0x18000499f  xor     rcx, rsp; StackCookie
0x1800049a2  call    __security_check_cookie
0x1800049a7  add     rsp, 48h
0x1800049ab  retn
```
