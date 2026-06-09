# GetRegQWordOrZero(HKEY__ *,ushort const *,_LLFILETIME *)

- ea: `0x180013264`
- end: `0x1800132d0`
- name: `?GetRegQWordOrZero@@YAXPEAUHKEY__@@PEBGPEAU_LLFILETIME@@@Z`
- size: `108`
- prototype: `void __fastcall(HKEY, const unsigned __int16 *, struct _LLFILETIME *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800108f8`

## callees

- `0x18000ebc0`
- `0x180013264`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013296`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180013296`

## string_xrefs

- `0x1800132b1`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
void __fastcall GetRegQWordOrZero(HKEY a1, const unsigned __int16 *a2, struct _LLFILETIME *a3)
{
  int ValueW; // eax
  bool v5; // sf
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD v7; // [rsp+68h] [rbp+20h] BYREF

  v7 = 8;
  ValueW = RegGetValueW(a1, 0, a2, 0x40u, 0, a3, &v7);
  v5 = ValueW < 0;
  if ( ValueW > 0 )
  {
    ValueW = (unsigned __int16)ValueW | 0x80070000;
    v5 = ValueW < 0;
  }
  if ( v5 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D0,
      (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
      (const char *)(unsigned int)ValueW);
    a3->ll = 0;
  }
}

```

## disassembly

```asm
0x180013264  mov     r11, rsp
0x180013267  push    rbx
0x180013268  sub     rsp, 40h
0x18001326c  mov     rbx, r8
0x18001326f  mov     [rsp+48h+arg_18], 8
0x180013277  lea     rax, [r11+20h]
0x18001327b  mov     r8, rdx; lpValue
0x18001327e  mov     [r11-18h], rax
0x180013282  mov     r9d, 40h ; '@'; dwFlags
0x180013288  mov     [r11-20h], rbx
0x18001328c  xor     edx, edx; lpSubKey
0x18001328e  mov     qword ptr [r11-28h], 0
0x180013296  call    cs:__imp_RegGetValueW
0x18001329c  test    eax, eax
0x18001329e  jle     short loc_1800132AA
0x1800132a0  movzx   eax, ax
0x1800132a3  or      eax, 80070000h
0x1800132a8  test    eax, eax
0x1800132aa  jns     short loc_1800132CA
0x1800132ac  mov     rcx, [rsp+48h]; this
0x1800132b1  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800132b8  mov     r9d, eax; char *
0x1800132bb  mov     edx, 2D0h; void *
0x1800132c0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800132c5  xor     eax, eax
0x1800132c7  mov     [rbx], rax
0x1800132ca  add     rsp, 40h
0x1800132ce  pop     rbx
0x1800132cf  retn
```
