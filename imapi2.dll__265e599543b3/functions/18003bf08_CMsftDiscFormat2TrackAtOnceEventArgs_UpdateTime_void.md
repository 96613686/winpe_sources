# CMsftDiscFormat2TrackAtOnceEventArgs::UpdateTime(void)

- ea: `0x18003bf08`
- end: `0x18003bf37`
- name: `?UpdateTime@CMsftDiscFormat2TrackAtOnceEventArgs@@AEAAXXZ`
- size: `47`
- prototype: `void __fastcall(CMsftDiscFormat2TrackAtOnceEventArgs *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800369e0`
- `0x180039320`
- `0x18003a784`
- `0x18003bd60`
- `0x18003bf60`
- `0x18003bfe0`

## callees

- `0x18003bf08`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x18003bf11`
- `KERNEL32!GetTickCount` at `0x18003bf11`

## pseudocode

```c
void __fastcall CMsftDiscFormat2TrackAtOnceEventArgs::UpdateTime(CMsftDiscFormat2TrackAtOnceEventArgs *this)
{
  DWORD v2; // kr00_4

  v2 = GetTickCount() - *((_DWORD *)this + 27);
  *((_DWORD *)this + 29) = v2 / 0x3E8;
  if ( (signed int)(v2 / 0x3E8) > *((_DWORD *)this + 28) )
    *((_DWORD *)this + 28) = v2 / 0x3E8;
}

```

## disassembly

```asm
0x18003bf08  push    rbx
0x18003bf0a  sub     rsp, 20h
0x18003bf0e  mov     rbx, rcx
0x18003bf11  call    cs:__imp_GetTickCount
0x18003bf17  mov     edx, eax
0x18003bf19  mov     eax, 10624DD3h
0x18003bf1e  sub     edx, [rbx+6Ch]
0x18003bf21  mul     edx
0x18003bf23  shr     edx, 6
0x18003bf26  mov     [rbx+74h], edx
0x18003bf29  cmp     edx, [rbx+70h]
0x18003bf2c  jle     short loc_18003BF31
0x18003bf2e  mov     [rbx+70h], edx
0x18003bf31  add     rsp, 20h
0x18003bf35  pop     rbx
0x18003bf36  retn
```
