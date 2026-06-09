# Microsoft::HostGuardian::Client::HgServicePlugin::~HgServicePlugin(void)

- ea: `0x180013ffc`
- end: `0x180014060`
- name: `??1HgServicePlugin@Client@HostGuardian@Microsoft@@UEAA@XZ`
- size: `100`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::HgServicePlugin *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c574`
- `0x180014070`
- `0x180015d81`
- `0x180015e72`

## callees

- `0x180004274`
- `0x180013ffc`
- `0x18001424c`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180014053`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180014053`

## string_xrefs

- `0x180014030`: `servercommon\base\securehostingservice\common\service\lib\hgserviceplugin.cpp`
- `0x180014021`: `Plugin uninitialzation failed.`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::HgServicePlugin::~HgServicePlugin(
        Microsoft::HostGuardian::Client::HgServicePlugin *this)
{
  unsigned int v2; // eax
  HMODULE v3; // rcx
  const char *v4; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)this = &Microsoft::HostGuardian::Client::HgServicePlugin::`vftable';
  v2 = (*((__int64 (__fastcall **)(_QWORD))this + 4))(*((_QWORD *)this + 2));
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x3A,
    (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgserviceplugin.cpp",
    (const char *)v2,
    (int)"Plugin uninitialzation failed.",
    v4);
  std::wstring::~wstring((char **)this + 13);
  v3 = (HMODULE)*((_QWORD *)this + 1);
  if ( v3 )
    FreeLibrary(v3);
}

```

## disassembly

```asm
0x180013ffc  push    rbx
0x180013ffe  sub     rsp, 30h
0x180014002  mov     rbx, rcx
0x180014005  lea     rax, ??_7HgServicePlugin@Client@HostGuardian@Microsoft@@6B@; const Microsoft::HostGuardian::Client::HgServicePlugin::`vftable'
0x18001400c  mov     [rcx], rax
0x18001400f  mov     rcx, [rcx+10h]
0x180014013  mov     rax, [rbx+20h]
0x180014017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001401c  mov     rcx, [rsp+38h]; this
0x180014021  lea     rdx, aPluginUninitia; "Plugin uninitialzation failed."
0x180014028  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18001402d  mov     r9d, eax; char *
0x180014030  lea     r8, aServercommonBa_4; "servercommon\\base\\securehostingservic"...
0x180014037  mov     edx, 3Ah ; ':'; void *
0x18001403c  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180014041  lea     rcx, [rbx+68h]
0x180014045  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001404a  mov     rcx, [rbx+8]; hLibModule
0x18001404e  test    rcx, rcx
0x180014051  jz      short loc_18001405A
0x180014053  call    cs:__imp_FreeLibrary
0x180014059  nop
0x18001405a  add     rsp, 30h
0x18001405e  pop     rbx
0x18001405f  retn
```
