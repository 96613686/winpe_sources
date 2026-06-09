# CMachineSettings::FinalConstruct(void)

- ea: `0x1800357b0`
- end: `0x180035884`
- name: `?FinalConstruct@CMachineSettings@@QEAAJXZ`
- size: `212`
- prototype: `__int64 __fastcall(CMachineSettings *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e600`
- `0x1800125d0`
- `0x18001280c`

## callees

- `0x180023834`
- `0x1800357b0`
- `0x1800538f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800357c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800357f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800357c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800357f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMachineSettings::FinalConstruct(CMachineSettings *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax
  _QWORD *v4; // rdi
  __int64 v5; // rbx

  v2 = CoTaskMemAlloc(0x10u);
  if ( v2 )
  {
    *v2 = 0;
    v2[1] = 0;
  }
  *((_QWORD *)this + 36) = v2;
  if ( !v2 )
    return 2147942414LL;
  v3 = CoTaskMemAlloc(0x40u);
  v4 = v3;
  if ( v3 )
  {
    v5 = *((_QWORD *)this + 36);
    v3[2] = 0;
    v3[3] = 17;
    v3[4] = 0;
    v3[6] = v3 + 5;
    v3[5] = v3 + 5;
    Map<unsigned short const *,HKEY__ *,HashWSTR,EmptyMapBase>::allocAssocIfNecessary((__int64)(v3 + 2));
    v4[7] = v5;
    *v4 = -2147483646;
    *((_DWORD *)v4 + 2) = 0;
  }
  else
  {
    v4 = 0;
  }
  *((_QWORD *)this + 35) = v4;
  if ( v4 )
    return CSimpleDataTableCursor::InitCache((CMachineSettings *)((char *)this + 40));
  else
    return 2147942414LL;
}

```

## disassembly

```asm
0x1800357b0  mov     [rsp+arg_10], rbx
0x1800357b5  mov     [rsp+arg_18], rsi
0x1800357ba  push    rdi
0x1800357bb  sub     rsp, 20h
0x1800357bf  mov     rsi, rcx
0x1800357c2  mov     ecx, 10h; cb
0x1800357c7  call    cs:__imp_CoTaskMemAlloc
0x1800357cd  mov     [rsp+28h+arg_0], rax
0x1800357d2  test    rax, rax
0x1800357d5  jz      short loc_1800357E6
0x1800357d7  mov     qword ptr [rax], 0
0x1800357de  mov     qword ptr [rax+8], 0
0x1800357e6  mov     [rsi+120h], rax
0x1800357ed  test    rax, rax
0x1800357f0  jz      short loc_18003586F
0x1800357f2  mov     ecx, 40h ; '@'; cb
0x1800357f7  call    cs:__imp_CoTaskMemAlloc
0x1800357fd  mov     rdi, rax
0x180035800  mov     [rsp+28h+arg_0], rax
0x180035805  test    rax, rax
0x180035808  jz      short loc_180035856
0x18003580a  mov     rbx, [rsi+120h]
0x180035811  lea     rcx, [rax+10h]
0x180035815  mov     [rsp+28h+arg_8], rcx
0x18003581a  mov     qword ptr [rcx], 0
0x180035821  mov     qword ptr [rcx+8], 11h
0x180035829  mov     qword ptr [rcx+10h], 0
0x180035831  lea     rdx, [rcx+18h]
0x180035835  mov     [rdx+8], rdx
0x180035839  mov     [rdx], rdx
0x18003583c  call    ?allocAssocIfNecessary@?$Map@PEBGPEAUHKEY__@@VHashWSTR@@VEmptyMapBase@@@@AEAAJXZ; Map<ushort const *,HKEY__ *,HashWSTR,EmptyMapBase>::allocAssocIfNecessary(void)
0x180035841  nop
0x180035842  mov     [rdi+38h], rbx
0x180035846  mov     qword ptr [rdi], 0FFFFFFFF80000002h
0x18003584d  mov     dword ptr [rdi+8], 0
0x180035854  jmp     short loc_180035858
0x180035856  xor     edi, edi
0x180035858  mov     [rsi+118h], rdi
0x18003585f  test    rdi, rdi
0x180035862  jz      short loc_18003586F
0x180035864  lea     rcx, [rsi+28h]; this
0x180035868  call    ?InitCache@CSimpleDataTableCursor@@QEAAJXZ; CSimpleDataTableCursor::InitCache(void)
0x18003586d  jmp     short loc_180035874
0x18003586f  mov     eax, 8007000Eh
0x180035874  mov     rbx, [rsp+28h+arg_10]
0x180035879  mov     rsi, [rsp+28h+arg_18]
0x18003587e  add     rsp, 20h
0x180035882  pop     rdi
0x180035883  retn
```
