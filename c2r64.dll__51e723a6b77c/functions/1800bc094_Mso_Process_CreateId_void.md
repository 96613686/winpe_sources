# Mso::Process::CreateId(void)

- ea: `0x1800bc094`
- end: `0x1800bc196`
- name: `?CreateId@Process@Mso@@YA_NXZ`
- size: `258`
- prototype: `bool __fastcall(Mso::Process *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800bbf60`

## callees

- `0x18003e690`
- `0x18009b040`
- `0x1800bbeb4`
- `0x1800bc094`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x1800bc0ed`
- `KERNEL32!CreateEventExW` at `0x1800bc0ed`
- `KERNEL32!CloseHandle` at `0x1800bc14c`
- `KERNEL32!CloseHandle` at `0x1800bc173`
- `KERNEL32!CloseHandle` at `0x1800bc14c`
- `KERNEL32!CloseHandle` at `0x1800bc173`
- `ole32!CoCreateGuid` at `0x1800bc0ba`
- `ole32!CoCreateGuid` at `0x1800bc0ba`
- `ole32!StringFromCLSID` at `0x1800bc0d4`
- `ole32!StringFromCLSID` at `0x1800bc0d4`
- `ole32!CoTaskMemFree` at `0x1800bc110`
- `ole32!CoTaskMemFree` at `0x1800bc18b`
- `ole32!CoTaskMemFree` at `0x1800bc110`
- `ole32!CoTaskMemFree` at `0x1800bc18b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Mso::Process::CreateId(Mso::Process *this)
{
  HANDLE Event; // rbx
  LPOLESTR v2; // rcx
  __int64 v4; // rcx
  LPOLESTR v5; // rcx
  LPOLESTR lpsz; // [rsp+20h] [rbp-30h] BYREF
  HANDLE hObject; // [rsp+28h] [rbp-28h] BYREF
  GUID pguid; // [rsp+30h] [rbp-20h] BYREF

  pguid = 0;
  if ( CoCreateGuid(&pguid) < 0 )
    return 0;
  lpsz = 0;
  if ( StringFromCLSID(&pguid, &lpsz) < 0 || (Event = CreateEventExW(0, lpsz, 0, 0x1F0003u), (hObject = Event) == 0) )
  {
LABEL_4:
    v2 = lpsz;
    if ( lpsz )
    {
      lpsz = 0;
      CoTaskMemFree(v2);
    }
    return 0;
  }
  if ( !(unsigned int)MsoFRegSetBinary(
                        (const struct _msoreg *)&vmsoridSessionId,
                        (const unsigned __int8 *)&pguid,
                        0x10u) )
  {
    CloseHandle(Event);
    goto LABEL_4;
  }
  xmmword_18021C380 = (__int128)pguid;
  Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::TransferFrom<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>(
    v4,
    &hObject);
  if ( hObject )
    CloseHandle(hObject);
  v5 = lpsz;
  if ( lpsz )
  {
    lpsz = 0;
    CoTaskMemFree(v5);
  }
  return 1;
}

```

## disassembly

```asm
0x1800bc094  mov     [rsp-8+arg_0], rbx
0x1800bc099  push    rbp
0x1800bc09a  mov     rbp, rsp
0x1800bc09d  sub     rsp, 50h
0x1800bc0a1  mov     rax, cs:__security_cookie
0x1800bc0a8  xor     rax, rsp
0x1800bc0ab  mov     [rbp+var_10], rax
0x1800bc0af  xorps   xmm0, xmm0
0x1800bc0b2  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x1800bc0b6  lea     rcx, [rbp+pguid]; pguid
0x1800bc0ba  call    cs:__imp_CoCreateGuid
0x1800bc0c0  test    eax, eax
0x1800bc0c2  js      short loc_1800BC116
0x1800bc0c4  mov     [rbp+lpsz], 0
0x1800bc0cc  lea     rdx, [rbp+lpsz]; lplpsz
0x1800bc0d0  lea     rcx, [rbp+pguid]; rclsid
0x1800bc0d4  call    cs:__imp_StringFromCLSID
0x1800bc0da  test    eax, eax
0x1800bc0dc  js      short loc_1800BC0FF
0x1800bc0de  mov     r9d, 1F0003h; dwDesiredAccess
0x1800bc0e4  xor     r8d, r8d; dwFlags
0x1800bc0e7  mov     rdx, [rbp+lpsz]; lpName
0x1800bc0eb  xor     ecx, ecx; lpEventAttributes
0x1800bc0ed  call    cs:__imp_CreateEventExW
0x1800bc0f3  mov     rbx, rax
0x1800bc0f6  mov     [rbp+hObject], rax
0x1800bc0fa  test    rax, rax
0x1800bc0fd  jnz     short loc_1800BC12F
0x1800bc0ff  mov     rcx, [rbp+lpsz]; pv
0x1800bc103  test    rcx, rcx
0x1800bc106  jz      short loc_1800BC116
0x1800bc108  mov     [rbp+lpsz], 0
0x1800bc110  call    cs:__imp_CoTaskMemFree
0x1800bc116  xor     al, al
0x1800bc118  mov     rcx, [rbp+var_10]
0x1800bc11c  xor     rcx, rsp; StackCookie
0x1800bc11f  call    __security_check_cookie
0x1800bc124  mov     rbx, [rsp+50h+arg_0]
0x1800bc129  add     rsp, 50h
0x1800bc12d  pop     rbp
0x1800bc12e  retn
0x1800bc12f  mov     r8d, 10h; unsigned int
0x1800bc135  lea     rdx, [rbp+pguid]; unsigned __int8 *
0x1800bc139  lea     rcx, ?vmsoridSessionId@@3U_msoreg@@B; struct _msoreg *
0x1800bc140  call    ?MsoFRegSetBinary@@YAHPEBU_msoreg@@PEBEK@Z; MsoFRegSetBinary(_msoreg const *,uchar const *,ulong)
0x1800bc145  test    eax, eax
0x1800bc147  jnz     short loc_1800BC155
0x1800bc149  mov     rcx, rbx; hObject
0x1800bc14c  call    cs:__imp_CloseHandle
0x1800bc152  nop
0x1800bc153  jmp     short loc_1800BC0FF
0x1800bc155  movups  xmm0, xmmword ptr [rbp+pguid.Data1]
0x1800bc159  movdqu  cs:xmmword_18021C380, xmm0
0x1800bc161  lea     rdx, [rbp+hObject]
0x1800bc165  call    ??$TransferFrom@PEAXUHandleHelper@Mso@@U?$EmptyTraits@PEAX@2@@?$THolder@PEAXUHandleHelper@Mso@@U?$EmptyTraits@PEAX@2@@Mso@@QEAAXAEAV01@@Z; Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>::TransferFrom<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>>(Mso::THolder<void *,Mso::HandleHelper,Mso::EmptyTraits<void *>> &)
0x1800bc16a  mov     rcx, [rbp+hObject]; hObject
0x1800bc16e  test    rcx, rcx
0x1800bc171  jz      short loc_1800BC17A
0x1800bc173  call    cs:__imp_CloseHandle
0x1800bc179  nop
0x1800bc17a  mov     rcx, [rbp+lpsz]; pv
0x1800bc17e  test    rcx, rcx
0x1800bc181  jz      short loc_1800BC191
0x1800bc183  mov     [rbp+lpsz], 0
0x1800bc18b  call    cs:__imp_CoTaskMemFree
0x1800bc191  mov     al, 1
0x1800bc193  jmp     short loc_1800BC118
```
