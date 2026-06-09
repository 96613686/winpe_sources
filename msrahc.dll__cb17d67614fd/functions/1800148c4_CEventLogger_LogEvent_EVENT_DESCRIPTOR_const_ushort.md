# CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)

- ea: `0x1800148c4`
- end: `0x18001494f`
- name: `?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z`
- size: `139`
- prototype: `__int64 __fastcall(CEventLogger *this, const struct _EVENT_DESCRIPTOR *, unsigned __int16 *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180010d70`
- `0x180010fc0`
- `0x1800114d0`
- `0x180011874`
- `0x180011a04`
- `0x1800171dc`

## callees

- `0x1800148c4`
- `0x180014958`
- `0x18001a5e0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180014926`
- `ADVAPI32!EventWrite` at `0x180014926`

## pseudocode

```c
__int64 __fastcall CEventLogger::LogEvent(CEventLogger *this, const struct _EVENT_DESCRIPTOR *a2, unsigned __int16 *a3)
{
  ULONGLONG v4; // r11
  unsigned __int64 v6; // [rsp+20h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+28h] [rbp-20h] BYREF

  v6 = 0;
  if ( (int)StringCbLengthW(a3, (unsigned __int64)a2, &v6) < 0 )
    return 2147500037LL;
  UserData.Size = v6 + 2;
  UserData.Ptr = v4;
  UserData.Reserved = 0;
  return EventWrite(g_Logger, a2, 1u, &UserData) != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x1800148c4  push    rbx
0x1800148c6  sub     rsp, 40h
0x1800148ca  mov     rax, cs:__security_cookie
0x1800148d1  xor     rax, rsp
0x1800148d4  mov     [rsp+48h+var_10], rax
0x1800148d9  mov     r11, r8
0x1800148dc  mov     [rsp+48h+var_28], 0
0x1800148e5  mov     rcx, r11; unsigned __int16 *
0x1800148e8  lea     r8, [rsp+48h+var_28]; unsigned __int64 *
0x1800148ed  mov     rbx, rdx
0x1800148f0  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800148f5  test    eax, eax
0x1800148f7  js      short loc_180014937
0x1800148f9  mov     eax, dword ptr [rsp+48h+var_28]
0x1800148fd  lea     r9, [rsp+48h+UserData]; UserData
0x180014902  mov     rcx, cs:?g_Logger@@3VCEventLogger@@A; RegHandle
0x180014909  add     eax, 2
0x18001490c  mov     r8d, 1; UserDataCount
0x180014912  mov     [rsp+48h+UserData.Size], eax
0x180014916  mov     rdx, rbx; EventDescriptor
0x180014919  mov     [rsp+48h+UserData.Ptr], r11
0x18001491e  mov     dword ptr [rsp+48h+UserData.0Ch], 0
0x180014926  call    cs:__imp_EventWrite
0x18001492c  neg     eax
0x18001492e  sbb     eax, eax
0x180014930  and     eax, 80004005h
0x180014935  jmp     short loc_18001493C
0x180014937  mov     eax, 80004005h
0x18001493c  mov     rcx, [rsp+48h+var_10]
0x180014941  xor     rcx, rsp; StackCookie
0x180014944  call    __security_check_cookie
0x180014949  add     rsp, 40h
0x18001494d  pop     rbx
0x18001494e  retn
```
