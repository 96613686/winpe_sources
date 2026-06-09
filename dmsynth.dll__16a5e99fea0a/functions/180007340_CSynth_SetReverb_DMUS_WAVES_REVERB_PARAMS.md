# CSynth::SetReverb(_DMUS_WAVES_REVERB_PARAMS *)

- ea: `0x180007340`
- end: `0x18000738b`
- name: `?SetReverb@CSynth@@QEAAJPEAU_DMUS_WAVES_REVERB_PARAMS@@@Z`
- size: `75`
- prototype: `__int64 __fastcall(CSynth *__hidden this, struct _DMUS_WAVES_REVERB_PARAMS *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005f60`
- `0x1800073a0`
- `0x180012130`

## callees

- `0x180002a40`
- `0x180007340`

## pseudocode

```c
__int64 __fastcall CSynth::SetReverb(CSynth *this, struct _DMUS_WAVES_REVERB_PARAMS *a2)
{
  __int64 v2; // rax

  v2 = *((_QWORD *)this + 19);
  *((struct _DMUS_WAVES_REVERB_PARAMS *)this + 10) = *a2;
  if ( v2 )
    SetSVerb(*((float *)this + 40), *((float *)this + 41), *((float *)this + 42), *((float *)this + 43), v2);
  return 0;
}

```

## disassembly

```asm
0x180007340  sub     rsp, 38h
0x180007344  movups  xmm0, xmmword ptr [rdx]
0x180007347  mov     rax, [rcx+98h]
0x18000734e  movups  xmmword ptr [rcx+0A0h], xmm0
0x180007355  test    rax, rax
0x180007358  jz      short loc_180007384
0x18000735a  movss   xmm3, dword ptr [rcx+0ACh]
0x180007362  movss   xmm2, dword ptr [rcx+0A8h]
0x18000736a  movss   xmm1, dword ptr [rcx+0A4h]
0x180007372  movss   xmm0, dword ptr [rcx+0A0h]
0x18000737a  mov     [rsp+38h+var_18], rax
0x18000737f  call    SetSVerb
0x180007384  xor     eax, eax
0x180007386  add     rsp, 38h
0x18000738a  retn
```
