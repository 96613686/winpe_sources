# _NGenQueue::DoWork_::_1_::catch$152

- ea: `0x18004158c`
- end: `0x1800417b9`
- name: `_NGenQueue::DoWork_::_1_::catch$152`
- size: `557`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001e8c`
- `0x180005c3c`
- `0x180005cec`
- `0x18002e418`
- `0x180030568`
- `0x180030d84`
- `0x180033ab4`
- `0x180034de4`
- `0x18003549c`
- `0x180036524`
- `0x1800366a8`
- `0x18003f1db`
- `0x18003f280`
- `0x18004158c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180041697`
- `OLEAUT32!__imp_SysAllocString` at `0x180041697`
- `OLEAUT32!__imp_SysFreeString` at `0x180041712`
- `OLEAUT32!__imp_SysFreeString` at `0x180041712`

## string_xrefs

- `0x1800416f6`: `Failed to execute command from the offline queue: %s.  The error returned was %s.`

## pseudocode

```c
__int64 __fastcall NGenQueue::DoWork_::_1_::catch_152(__int64 a1, __int64 a2, bool a3)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  OLECHAR *v6; // rbx
  Exception *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned int CurrentExceptionCode; // eax
  int v11; // edx

  *(_QWORD *)(a2 + 416) = &Exception::`vftable';
  *(_QWORD *)(a2 + 424) = 0;
  *(_QWORD *)(a2 + 416) = &DelegatingException::`vftable';
  *(_QWORD *)(a2 + 432) = -1;
  v4 = *(_QWORD *)(a2 + 288);
  *(_QWORD *)(a2 + 320) = v4;
  *(_DWORD *)(a2 + 328) = 0;
  *(_DWORD *)(a2 + 328) = v4 != 0;
  Exception::HandlerState::SetupCatch((Exception::HandlerState *)(a2 + 280), 377, a3);
  v5 = a2 + 416;
  if ( *(_QWORD *)(a2 + 320) )
    v5 = *(_QWORD *)(a2 + 320);
  *(_DWORD *)(a2 + 1664) = 0;
  *(_DWORD *)(a2 + 1668) = 0;
  *(_DWORD *)(a2 + 1672) = 0;
  *(_QWORD *)(a2 + 1680) = 0;
  *(_QWORD *)(a2 + 1680) = a2 + 1688;
  *(_DWORD *)(a2 + 1668) = 512;
  *(_DWORD *)(a2 + 1664) = 2;
  **(_WORD **)(a2 + 1680) = 0;
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 24LL))(v5, a2 + 1664);
  SString::Append((SString *)(a2 + 1664), L"\n");
  SString::ConvertToUnicode((SString *)(a2 + 1664));
  v6 = SysAllocString(*(const OLECHAR **)(a2 + 1680));
  *(_QWORD *)(a2 + 440) = v6;
  *(_DWORD *)(a2 + 448) = 0;
  *(_DWORD *)(a2 + 448) = v6 != 0;
  (*(void (__fastcall **)(_QWORD, __int64, OLECHAR *))(**(_QWORD **)(a2 + 400) + 24LL))(*(_QWORD *)(a2 + 400), 1, v6);
  if ( NGENService::g_bProcessNGENService )
    NGENService::EventLog(
      0,
      (const unsigned __int16 *)1,
      0x453u,
      (unsigned int)L"Failed to execute command from the offline queue: %s.  The error returned was %s.",
      *(const unsigned __int16 **)(a2 + 80),
      v6);
  if ( v6 )
  {
    SysFreeString(v6);
    *(_DWORD *)(a2 + 448) = 0;
  }
  if ( (*(_BYTE *)(a2 + 1672) & 8) != 0 )
    operator delete(*(void **)(a2 + 1680));
  v7 = (Exception *)(a2 + 416);
  if ( *(_QWORD *)(a2 + 320) )
    v7 = *(Exception **)(a2 + 320);
  if ( (unsigned int)Exception::IsTerminal(v7)
    || !(unsigned int)CLRConfig::GetConfigValue(
                        (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::UNSUPPORTED_legacyCorruptedStateExceptionsPolicy,
                        v8,
                        (bool *)(a2 + 168),
                        v9)
    && (CurrentExceptionCode = GetCurrentExceptionCode(),
        (unsigned int)IsProcessCorruptedStateException(CurrentExceptionCode, v11)) )
  {
    *(_DWORD *)(a2 + 328) = 0;
    throw;
  }
  Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2,1>::~Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2,1>((__int64 *)(a2 + 320));
  DelegatingException::~DelegatingException((DelegatingException *)(a2 + 416));
  return 0;
}

```

## disassembly

```asm
0x18004158c  mov     [rsp+arg_8], rdx
0x180041591  push    rbx
0x180041592  push    rbp
0x180041593  push    rdi
0x180041594  sub     rsp, 30h
0x180041598  mov     rbp, rdx
0x18004159b  lea     rax, ??_7Exception@@6B@; const Exception::`vftable'
0x1800415a2  mov     [rbp+1A0h], rax
0x1800415a9  and     qword ptr [rbp+1A8h], 0
0x1800415b1  lea     rax, ??_7DelegatingException@@6B@; const DelegatingException::`vftable'
0x1800415b8  mov     [rbp+1A0h], rax
0x1800415bf  or      qword ptr [rbp+1B0h], 0FFFFFFFFFFFFFFFFh
0x1800415c7  mov     rax, [rbp+120h]
0x1800415ce  mov     [rbp+140h], rax
0x1800415d5  xor     ecx, ecx
0x1800415d7  mov     [rbp+148h], ecx
0x1800415dd  lea     edx, [rcx+1]
0x1800415e0  test    rax, rax
0x1800415e3  cmovnz  ecx, edx
0x1800415e6  mov     [rbp+148h], ecx
0x1800415ec  mov     edx, 179h; int
0x1800415f1  lea     rcx, [rbp+118h]; this
0x1800415f8  call    ?SetupCatch@HandlerState@Exception@@QEAAXH_N@Z; Exception::HandlerState::SetupCatch(int,bool)
0x1800415fd  lea     rcx, [rbp+1A0h]
0x180041604  mov     rax, [rbp+140h]
0x18004160b  test    rax, rax
0x18004160e  cmovnz  rcx, rax
0x180041612  and     dword ptr [rbp+680h], 0
0x180041619  and     dword ptr [rbp+684h], 0
0x180041620  and     dword ptr [rbp+688h], 0
0x180041627  and     qword ptr [rbp+690h], 0
0x18004162f  lea     rax, [rbp+698h]
0x180041636  mov     [rbp+690h], rax
0x18004163d  mov     dword ptr [rbp+684h], 200h
0x180041647  mov     dword ptr [rbp+680h], 2
0x180041651  xor     edx, edx
0x180041653  mov     rax, [rbp+690h]
0x18004165a  mov     [rax], dx
0x18004165d  mov     rax, [rcx]
0x180041660  lea     rdx, [rbp+680h]
0x180041667  mov     rax, [rax+18h]
0x18004166b  call    cs:__guard_dispatch_icall_fptr
0x180041671  lea     rdx, asc_180051EB0; "\n"
0x180041678  lea     rcx, [rbp+680h]; this
0x18004167f  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180041684  lea     rcx, [rbp+680h]; this
0x18004168b  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180041690  mov     rcx, [rbp+690h]; psz
0x180041697  call    cs:__imp_SysAllocString
0x18004169d  mov     rbx, rax
0x1800416a0  mov     [rbp+1B8h], rax
0x1800416a7  xor     edi, edi
0x1800416a9  mov     [rbp+1C0h], edi
0x1800416af  lea     eax, [rdi+1]
0x1800416b2  test    rbx, rbx
0x1800416b5  cmovnz  edi, eax
0x1800416b8  mov     [rbp+1C0h], edi
0x1800416be  mov     rcx, [rbp+190h]
0x1800416c5  mov     rax, [rcx]
0x1800416c8  mov     r8, rbx
0x1800416cb  mov     edx, 1
0x1800416d0  mov     rax, [rax+18h]
0x1800416d4  call    cs:__guard_dispatch_icall_fptr
0x1800416da  cmp     cs:?g_bProcessNGENService@NGENService@@3_NA, 0; bool NGENService::g_bProcessNGENService
0x1800416e1  jz      short loc_18004170B
0x1800416e3  mov     edx, 1; unsigned __int16 *
0x1800416e8  mov     [rsp+48h+var_20], rbx
0x1800416ed  mov     rax, [rbp+50h]
0x1800416f1  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x1800416f6  lea     r9, aFailedToExecut; "Failed to execute command from the offl"...
0x1800416fd  xor     ecx, ecx; this
0x1800416ff  mov     r8d, 453h; unsigned __int16
0x180041705  call    ?EventLog@NGENService@@YAXPEBGGK0ZZ; NGENService::EventLog(ushort const *,ushort,ulong,ushort const *,...)
0x18004170a  nop
0x18004170b  test    edi, edi
0x18004170d  jz      short loc_18004171F
0x18004170f  mov     rcx, rbx; bstrString
0x180041712  call    cs:__imp_SysFreeString
0x180041718  and     dword ptr [rbp+1C0h], 0
0x18004171f  test    byte ptr [rbp+688h], 8
0x180041726  jz      short loc_180041734
0x180041728  mov     rcx, [rbp+690h]; lpMem
0x18004172f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180041734  lea     rcx, [rbp+1A0h]
0x18004173b  mov     rax, [rbp+140h]
0x180041742  test    rax, rax
0x180041745  cmovnz  rcx, rax; this
0x180041749  call    ?IsTerminal@Exception@@QEAAHXZ; Exception::IsTerminal(void)
0x18004174e  test    eax, eax
0x180041750  jnz     short loc_18004179F
0x180041752  lea     r8, [rbp+0A8h]; bool *
0x180041759  lea     rcx, ?UNSUPPORTED_legacyCorruptedStateExceptionsPolicy@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x180041760  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x180041765  test    eax, eax
0x180041767  jnz     short loc_180041779
0x180041769  call    ?GetCurrentExceptionCode@@YAKXZ; GetCurrentExceptionCode(void)
0x18004176e  mov     ecx, eax; unsigned int
0x180041770  call    ?IsProcessCorruptedStateException@@YAHKH@Z; IsProcessCorruptedStateException(ulong,int)
0x180041775  test    eax, eax
0x180041777  jnz     short loc_18004179F
0x180041779  lea     rcx, [rbp+140h]
0x180041780  call    ??1?$Wrapper@PEAVException@@$1??$DoNothing@PEAVException@@@@YAXPEAV1@@Z$1??$Exception__Delete@VException@@@@YAX0@Z$0A@$1??$CompareDefault@PEAVException@@@@YAH00@Z$01$00@@QEAA@XZ; Wrapper<Exception *,&DoNothing<Exception *>(Exception *),&Exception__Delete<Exception>(Exception *),0,&CompareDefault<Exception *>(Exception *,Exception *),2,1>::~Wrapper<Exception *,&DoNothing<Exception *>(Exception *),&Exception__Delete<Exception>(Exception *),0,&CompareDefault<Exception *>(Exception *,Exception *),2,1>(void)
0x180041785  nop
0x180041786  lea     rcx, [rbp+1A0h]; this
0x18004178d  call    ??1DelegatingException@@UEAA@XZ; DelegatingException::~DelegatingException(void)
0x180041792  nop
0x180041793  mov     rax, 0
0x18004179d  jmp     short loc_1800417B0
0x18004179f  and     dword ptr [rbp+148h], 0
0x1800417a6  xor     edx, edx; pThrowInfo
0x1800417a8  xor     ecx, ecx; pExceptionObject
0x1800417aa  call    _CxxThrowException_0
0x1800417b0  add     rsp, 30h
0x1800417b4  pop     rdi
0x1800417b5  pop     rbp
0x1800417b6  pop     rbx
0x1800417b7  retn
```
