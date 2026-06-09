# CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)

- ea: `0x180014814`
- end: `0x1800148bb`
- name: `?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z`
- size: `167`
- prototype: `__int64 __fastcall(CEventLogger *this, const struct _EVENT_DESCRIPTOR *, int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180013b00`
- `0x180013e40`

## callees

- `0x180014814`
- `0x180014958`
- `0x18001a5e0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x18001488e`
- `ADVAPI32!EventWrite` at `0x18001488e`

## pseudocode

```c
__int64 __fastcall CEventLogger::LogEvent(
        CEventLogger *this,
        const struct _EVENT_DESCRIPTOR *a2,
        int a3,
        unsigned __int16 *a4)
{
  const EVENT_DESCRIPTOR *v4; // r11
  unsigned __int64 v6; // [rsp+20h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+28h] [rbp-28h] BYREF
  const unsigned __int16 *v8; // [rsp+38h] [rbp-18h]
  int v9; // [rsp+40h] [rbp-10h]
  int v10; // [rsp+44h] [rbp-Ch]
  int v11; // [rsp+70h] [rbp+20h] BYREF

  v11 = a3;
  v6 = 0;
  if ( (int)StringCbLengthW(L"base\\diagnosis\\ra\\rahelperclass\\rasmapi.cpp", (unsigned __int64)a2, &v6) < 0 )
    return 2147500037LL;
  UserData.Ptr = (ULONGLONG)&v11;
  *(_QWORD *)&UserData.Size = 4;
  v9 = v6 + 2;
  v8 = L"base\\diagnosis\\ra\\rahelperclass\\rasmapi.cpp";
  v10 = 0;
  return EventWrite(g_Logger, v4, 2u, &UserData) != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x180014814  mov     [rsp-8+arg_0], rdi
0x180014819  mov     [rsp-8+arg_10], r8d
0x18001481e  push    rbp
0x18001481f  mov     rbp, rsp
0x180014822  sub     rsp, 50h
0x180014826  mov     rax, cs:__security_cookie
0x18001482d  xor     rax, rsp
0x180014830  mov     [rbp+var_8], rax
0x180014834  lea     rdi, aBaseDiagnosisR_7; "base\\diagnosis\\ra\\rahelperclass\\ras"...
0x18001483b  mov     [rbp+var_30], 0
0x180014843  mov     rcx, rdi; unsigned __int16 *
0x180014846  lea     r8, [rbp+var_30]; unsigned __int64 *
0x18001484a  mov     r11, rdx
0x18001484d  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180014852  test    eax, eax
0x180014854  js      short loc_18001489F
0x180014856  mov     rcx, cs:?g_Logger@@3VCEventLogger@@A; RegHandle
0x18001485d  lea     rax, [rbp+arg_10]
0x180014861  mov     [rbp+UserData.Ptr], rax
0x180014865  lea     r9, [rbp+UserData]; UserData
0x180014869  mov     eax, dword ptr [rbp+var_30]
0x18001486c  mov     r8d, 2; UserDataCount
0x180014872  add     eax, 2
0x180014875  mov     qword ptr [rbp+UserData.Size], 4
0x18001487d  mov     rdx, r11; EventDescriptor
0x180014880  mov     [rbp+var_10], eax
0x180014883  mov     [rbp+var_18], rdi
0x180014887  mov     [rbp+var_C], 0
0x18001488e  call    cs:__imp_EventWrite
0x180014894  neg     eax
0x180014896  sbb     eax, eax
0x180014898  and     eax, 80004005h
0x18001489d  jmp     short loc_1800148A4
0x18001489f  mov     eax, 80004005h
0x1800148a4  mov     rcx, [rbp+var_8]
0x1800148a8  xor     rcx, rsp; StackCookie
0x1800148ab  call    __security_check_cookie
0x1800148b0  mov     rdi, [rsp+50h+arg_0]
0x1800148b5  add     rsp, 50h
0x1800148b9  pop     rbp
0x1800148ba  retn
```
