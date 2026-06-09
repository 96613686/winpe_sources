# GetRegDWordOrZero(HKEY__ *,ushort const *,ulong *)

- ea: `0x180013220`
- end: `0x18001325d`
- name: `?GetRegDWordOrZero@@YAXPEAUHKEY__@@PEBGPEAK@Z`
- size: `61`
- prototype: `void __fastcall(NgcUtils *, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800108f8`

## callees

- `0x18000ebc0`
- `0x180013220`
- `0x18001cb68`

## string_xrefs

- `0x18001323d`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
void __fastcall GetRegDWordOrZero(NgcUtils *a1, unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int RegistryDwordValue; // eax
  unsigned int *v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  RegistryDwordValue = NgcUtils::GetRegistryDwordValue(a1, (HKEY)a2, a2, a3, v5);
  if ( RegistryDwordValue < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2B5,
      (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)RegistryDwordValue);
    *(_DWORD *)a3 = 0;
  }
}

```

## disassembly

```asm
0x180013220  push    rbx; int
0x180013222  sub     rsp, 20h
0x180013226  mov     rbx, r8
0x180013229  mov     r9, r8; unsigned __int16 *
0x18001322c  mov     r8, rdx; unsigned __int16 *
0x18001322f  call    ?GetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1PEAK@Z; NgcUtils::GetRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180013234  test    eax, eax
0x180013236  jns     short loc_180013257
0x180013238  mov     rcx, [rsp+28h]; this
0x18001323d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180013244  mov     r9d, eax; char *
0x180013247  mov     edx, 2B5h; void *
0x18001324c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180013251  mov     dword ptr [rbx], 0
0x180013257  add     rsp, 20h
0x18001325b  pop     rbx
0x18001325c  retn
```
