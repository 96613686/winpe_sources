# IIS_GLOBALMODULE::OnGlobalConfigurationChange(IGlobalConfigurationChangeProvider *)

- ea: `0x18000e510`
- end: `0x18000e5df`
- name: `?OnGlobalConfigurationChange@IIS_GLOBALMODULE@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalConfigurationChangeProvider@@@Z`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x180001008`
- `0x180001048`
- `0x180009b4c`
- `0x18000a028`
- `0x18000abfc`
- `0x18000e510`
- `0x18000edde`
- `0x180010010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000e52f`
- `msvcrt!_wcsicmp` at `0x18000e52f`

## pseudocode

```c
__int64 __fastcall IIS_GLOBALMODULE::OnGlobalConfigurationChange(__int64 a1, __int64 a2)
{
  const wchar_t *v2; // rax
  _DWORD *v3; // rax
  _DWORD *v4; // rbx

  v2 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  if ( !_wcsicmp(v2, L"MACHINE/WEBROOT/APPHOST") )
  {
    v3 = operator new(0x478u);
    v4 = v3;
    if ( v3 )
    {
      v3[262] = 0;
      memset_0(v3, 0, 0x418u);
      v4[264] = 0;
      *((_QWORD *)v4 + 133) = 0;
      *((_QWORD *)v4 + 134) = 0;
      v4[270] = 0;
      *(_QWORD *)(v4 + 271) = 1128743750;
      v4[284] = 0;
      if ( (int)IIS_CONFIG::Initialize((IIS_CONFIG *)v4) >= 0 )
        IIS_CONFIG::Update(IIS_FACTORY::sm_pConfig, (struct IIS_CONFIG *)v4);
      IIS_CONFIG::~IIS_CONFIG((IIS_CONFIG *)v4);
      operator delete(v4);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000e510  push    rbx
0x18000e512  sub     rsp, 20h
0x18000e516  mov     rax, [rdx]
0x18000e519  mov     rcx, rdx
0x18000e51c  mov     rax, [rax+8]
0x18000e520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e525  mov     rcx, rax; String1
0x18000e528  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18000e52f  call    cs:__imp__wcsicmp
0x18000e535  test    eax, eax
0x18000e537  jnz     loc_18000E5D7
0x18000e53d  mov     ecx, 478h; Size
0x18000e542  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e547  mov     rbx, rax
0x18000e54a  test    rax, rax
0x18000e54d  jz      loc_18000E5D7
0x18000e553  xor     edx, edx; Val
0x18000e555  mov     dword ptr [rax+418h], 0
0x18000e55f  mov     r8d, 418h; Size
0x18000e565  mov     rcx, rax; void *
0x18000e568  call    memset_0
0x18000e56d  mov     rcx, rbx; this
0x18000e570  mov     dword ptr [rbx+420h], 0
0x18000e57a  mov     qword ptr [rbx+428h], 0
0x18000e585  mov     qword ptr [rbx+430h], 0
0x18000e590  mov     dword ptr [rbx+438h], 0
0x18000e59a  mov     qword ptr [rbx+43Ch], 43474346h
0x18000e5a5  mov     dword ptr [rbx+470h], 0
0x18000e5af  call    ?Initialize@IIS_CONFIG@@QEAAJXZ; IIS_CONFIG::Initialize(void)
0x18000e5b4  test    eax, eax
0x18000e5b6  js      short loc_18000E5C7
0x18000e5b8  mov     rcx, cs:?sm_pConfig@IIS_FACTORY@@0PEAVIIS_CONFIG@@EA; this
0x18000e5bf  mov     rdx, rbx; struct IIS_CONFIG *
0x18000e5c2  call    ?Update@IIS_CONFIG@@QEAAJPEAV1@@Z; IIS_CONFIG::Update(IIS_CONFIG *)
0x18000e5c7  mov     rcx, rbx; this
0x18000e5ca  call    ??1IIS_CONFIG@@QEAA@XZ; IIS_CONFIG::~IIS_CONFIG(void)
0x18000e5cf  mov     rcx, rbx; Block
0x18000e5d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e5d7  xor     eax, eax
0x18000e5d9  add     rsp, 20h
0x18000e5dd  pop     rbx
0x18000e5de  retn
```
