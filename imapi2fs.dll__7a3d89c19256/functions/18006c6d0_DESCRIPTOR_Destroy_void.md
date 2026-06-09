# DESCRIPTOR::Destroy(void)

- ea: `0x18006c6d0`
- end: `0x18006c71b`
- name: `?Destroy@DESCRIPTOR@@AEAAXXZ`
- size: `75`
- prototype: `void __fastcall(DESCRIPTOR *__hidden this)`
- caller_count: `39`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001f4b4`
- `0x1800613e8`
- `0x180061684`
- `0x18006275c`
- `0x180062f38`
- `0x180063a90`
- `0x180064670`
- `0x180065438`
- `0x1800663c0`
- `0x180066570`
- `0x180067aec`
- `0x18006800c`
- `0x180068628`
- `0x180068858`
- `0x180068a9c`
- `0x180068ea0`
- `0x18006a43c`
- `0x18006a9dc`
- `0x18006af98`
- `0x18006b144`
- `0x18006c50c`
- `0x18006c5e4`
- `0x18006c810`
- `0x18006ca70`
- `0x18006d540`
- `0x18006e10c`
- `0x18006f3a0`
- `0x18006fad0`
- `0x1800706ac`
- `0x180070d28`
- `0x180070fd4`
- `0x180071944`
- `0x1800722b4`
- `0x1800723d0`
- `0x1800728b8`
- `0x180073994`
- `0x180074790`
- `0x180075990`
- `0x180076a94`

## callees

- `0x18006c6d0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18006c703`
- `ntdll!RtlFreeHeap` at `0x18006c703`

## pseudocode

```c
void __fastcall DESCRIPTOR::Destroy(DESCRIPTOR *this)
{
  void *v2; // r8

  *((_DWORD *)this + 7) = 0;
  *((_WORD *)this + 12) = 0;
  if ( *((_BYTE *)this + 26) )
  {
    v2 = (void *)*((_QWORD *)this + 2);
    if ( v2 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
      *((_QWORD *)this + 2) = 0;
    }
  }
  *((_BYTE *)this + 26) = 0;
}

```

## disassembly

```asm
0x18006c6d0  push    rbx
0x18006c6d2  sub     rsp, 20h
0x18006c6d6  xor     eax, eax
0x18006c6d8  mov     dword ptr [rcx+1Ch], 0
0x18006c6df  mov     rbx, rcx
0x18006c6e2  mov     [rcx+18h], ax
0x18006c6e6  cmp     [rcx+1Ah], al
0x18006c6e9  jz      short loc_18006C711
0x18006c6eb  mov     r8, [rcx+10h]; P
0x18006c6ef  test    r8, r8
0x18006c6f2  jz      short loc_18006C711
0x18006c6f4  mov     rcx, gs:60h
0x18006c6fd  xor     edx, edx; Flags
0x18006c6ff  mov     rcx, [rcx+30h]; HeapHandle
0x18006c703  call    cs:__imp_RtlFreeHeap
0x18006c709  mov     qword ptr [rbx+10h], 0
0x18006c711  mov     byte ptr [rbx+1Ah], 0
0x18006c715  add     rsp, 20h
0x18006c719  pop     rbx
0x18006c71a  retn
```
