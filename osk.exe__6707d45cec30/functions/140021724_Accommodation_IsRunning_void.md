# Accommodation::IsRunning(void)

- ea: `0x140021724`
- end: `0x1400217a7`
- name: `?IsRunning@Accommodation@@QEAAHXZ`
- size: `131`
- prototype: `__int64 __fastcall(Accommodation *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001e0e0`

## callees

- `0x140021580`
- `0x140021724`
- `0x140021d0c`
- `0x140025d42`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14002178f`
- `KERNEL32!CloseHandle` at `0x14002178f`
- `msvcrt!_wtoi` at `0x14002174c`
- `msvcrt!_wtoi` at `0x14002174c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Accommodation::IsRunning(const wchar_t **this)
{
  unsigned int v2; // edi
  unsigned int v3; // eax
  const unsigned __int16 *v4; // rcx
  HANDLE hObject; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  if ( !wcscmp_0(this[5], L"SystemSetting") )
  {
    v3 = _wtoi(this[3]);
    if ( v3 < 0x16 )
      return (unsigned int)SystemSettings::IsOn(this, v3);
  }
  else
  {
    v4 = this[7];
    if ( !*((_DWORD *)v4 - 4) )
      return 0;
    hObject = 0;
    if ( (unsigned int)Accommodation::FindProcess(v4, &hObject) )
    {
      CloseHandle(hObject);
      return 1;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140021724  mov     [rsp+arg_0], rbx
0x140021729  push    rdi
0x14002172a  sub     rsp, 20h
0x14002172e  mov     rbx, rcx
0x140021731  xor     edi, edi
0x140021733  lea     rdx, aSystemsetting; "SystemSetting"
0x14002173a  mov     rcx, [rcx+28h]; String1
0x14002173e  call    wcscmp_0
0x140021743  nop
0x140021744  test    eax, eax
0x140021746  jnz     short loc_140021765
0x140021748  mov     rcx, [rbx+18h]; String
0x14002174c  call    cs:__imp__wtoi
0x140021752  cmp     eax, 16h
0x140021755  jnb     short loc_14002179A
0x140021757  mov     edx, eax
0x140021759  mov     rcx, rbx
0x14002175c  call    ?IsOn@SystemSettings@@SAHAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@I@Z; SystemSettings::IsOn(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uint)
0x140021761  mov     edi, eax
0x140021763  jmp     short loc_14002179A
0x140021765  mov     rcx, [rbx+38h]; unsigned __int16 *
0x140021769  cmp     dword ptr [rcx-10h], 0
0x14002176d  jnz     short loc_140021773
0x14002176f  xor     eax, eax
0x140021771  jmp     short loc_14002179C
0x140021773  mov     [rsp+28h+hObject], 0
0x14002177c  lea     rdx, [rsp+28h+hObject]; void **
0x140021781  call    ?FindProcess@Accommodation@@SAKPEBGPEAPEAXH@Z; Accommodation::FindProcess(ushort const *,void * *,int)
0x140021786  test    eax, eax
0x140021788  jz      short loc_14002179A
0x14002178a  mov     rcx, [rsp+28h+hObject]; hObject
0x14002178f  call    cs:__imp_CloseHandle
0x140021795  mov     edi, 1
0x14002179a  mov     eax, edi
0x14002179c  mov     rbx, [rsp+28h+arg_0]
0x1400217a1  add     rsp, 20h
0x1400217a5  pop     rdi
0x1400217a6  retn
```
