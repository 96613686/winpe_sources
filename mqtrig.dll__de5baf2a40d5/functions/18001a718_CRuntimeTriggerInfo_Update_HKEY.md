# CRuntimeTriggerInfo::Update(HKEY__ *)

- ea: `0x18001a718`
- end: `0x18001a7bf`
- name: `?Update@CRuntimeTriggerInfo@@QEAA_NPEAUHKEY__@@@Z`
- size: `167`
- prototype: `bool __fastcall(CRuntimeTriggerInfo *__hidden this, HKEY)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180012770`
- `0x180012f40`

## callees

- `0x180004d88`
- `0x18000a2b8`
- `0x180019f58`
- `0x18001a15c`
- `0x18001a718`

## pseudocode

```c
bool __fastcall CRuntimeTriggerInfo::Update(CRuntimeTriggerInfo *this, HKEY a2)
{
  const wchar_t **v3; // rax
  const wchar_t *v4; // r8
  HKEY TriggerKeyHandle; // rax
  bool result; // al
  HKEY v7; // [rsp+40h] [rbp+18h] BYREF
  HKEY v8; // [rsp+48h] [rbp+20h] BYREF

  v3 = (const wchar_t **)*((_QWORD *)this + 260);
  if ( v3 )
    v4 = *v3;
  else
    v4 = 0;
  TriggerKeyHandle = CRuntimeTriggerInfo::GetTriggerKeyHandle(this, a2, v4);
  v7 = TriggerKeyHandle;
  if ( !TriggerKeyHandle )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
LABEL_8:
    CRegHandle::~CRegHandle(&v7);
    return 0;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v8 = TriggerKeyHandle;
    CRuntimeTriggerInfo::FlushValuesToRegistry(this, &v8);
    CRegHandle::~CRegHandle(&v7);
    result = 1;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18001A7AD);
      goto LABEL_8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001a718  mov     [rsp+arg_0], rcx
0x18001a71d  push    rbx
0x18001a71e  sub     rsp, 20h
0x18001a722  mov     rbx, rcx
0x18001a725  mov     rax, [rcx+820h]
0x18001a72c  test    rax, rax
0x18001a72f  jz      short loc_18001A736
0x18001a731  mov     r8, [rax]
0x18001a734  jmp     short loc_18001A739
0x18001a736  xor     r8d, r8d; wchar_t *
0x18001a739  call    ?GetTriggerKeyHandle@CRuntimeTriggerInfo@@AEAAPEAUHKEY__@@PEAU2@PEB_W@Z; CRuntimeTriggerInfo::GetTriggerKeyHandle(HKEY__ *,wchar_t const *)
0x18001a73e  mov     [rsp+28h+arg_10], rax
0x18001a743  test    rax, rax
0x18001a746  jnz     short loc_18001A78C
0x18001a748  lea     rax, WPP_GLOBAL_Control
0x18001a74f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a756  cmp     rcx, rax
0x18001a759  jz      short loc_18001A7AD
0x18001a75b  test    byte ptr [rcx+1Ch], 1
0x18001a75f  jz      short loc_18001A7AD
0x18001a761  mov     rax, [rbx+820h]
0x18001a768  test    rax, rax
0x18001a76b  jz      short loc_18001A772
0x18001a76d  mov     r9, [rax]
0x18001a770  jmp     short loc_18001A775
0x18001a772  xor     r9d, r9d
0x18001a775  mov     edx, 11h
0x18001a77a  lea     r8, WPP_5d468cdb8ea734f7fb134a242ccb11b7_Traceguids
0x18001a781  mov     rcx, [rcx+10h]; LoggerHandle
0x18001a785  call    WPP_SF_S
0x18001a78a  jmp     short loc_18001A7AD
0x18001a78c  mov     [rsp+28h+arg_18], rax
0x18001a791  lea     rdx, [rsp+28h+arg_18]; HKEY *
0x18001a796  mov     rcx, rbx; this
0x18001a799  call    ?FlushValuesToRegistry@CRuntimeTriggerInfo@@AEAAXAEBQEAUHKEY__@@@Z; CRuntimeTriggerInfo::FlushValuesToRegistry(HKEY__ * const &)
0x18001a79e  nop
0x18001a79f  lea     rcx, [rsp+28h+arg_10]; this
0x18001a7a4  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x18001a7a9  mov     al, 1
0x18001a7ab  jmp     short loc_18001A7B9
0x18001a7ad  lea     rcx, [rsp+28h+arg_10]; this
0x18001a7b2  call    ??1CRegHandle@@QEAA@XZ; CRegHandle::~CRegHandle(void)
0x18001a7b7  xor     al, al
0x18001a7b9  add     rsp, 20h
0x18001a7bd  pop     rbx
0x18001a7be  retn
```
