# VirtualChannel::Create(void *,ulong,char const *,_KEVENT *,RefCount *,int,int,int)

- ea: `0x14001b144`
- end: `0x14001b207`
- name: `?Create@VirtualChannel@@QEAAHPEAXKPEBDPEAU_KEVENT@@PEAVRefCount@@HHH@Z`
- size: `195`
- prototype: `int(VirtualChannel *__hidden this, void *, unsigned int, const char *, struct _KEVENT *, struct RefCount *, int, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14001bf2c`

## callees

- `0x140001660`
- `0x140001890`
- `0x14001b144`
- `0x14001b210`
- `0x14001b4d0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14001b1e8`
- `ntoskrnl!KeSetEvent` at `0x14001b1e8`

## pseudocode

```c
__int64 __fastcall VirtualChannel::Create(
        VirtualChannel *this,
        void *a2,
        unsigned int a3,
        const char *a4,
        struct _KEVENT *a5,
        struct RefCount *a6,
        int a7,
        int a8)
{
  RefCount *v10; // rcx
  void **v12; // rcx
  int TermDD; // eax
  struct _KEVENT *v15; // rcx

  *((_QWORD *)this + 20) = a5;
  v10 = (RefCount *)*((_QWORD *)this + 21);
  if ( v10 )
    RefCount::Release(v10);
  *((_QWORD *)this + 21) = a6;
  if ( a6 )
    RefCount::AddRef(a6);
  v12 = (void **)((char *)this + 24);
  *((_DWORD *)this + 44) = a8;
  *((_DWORD *)this + 45) = 0;
  if ( a8 )
    TermDD = ReferenceRdpExtensionChannel(v12, a2, a3, a4);
  else
    TermDD = CreateTermDD(v12, a2, a3, "RDPDR", a7);
  if ( TermDD >= 0 )
    return 1;
  v15 = (struct _KEVENT *)*((_QWORD *)this + 20);
  if ( v15 )
    KeSetEvent(v15, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x14001b144  mov     [rsp+arg_0], rbx
0x14001b149  mov     [rsp+arg_8], rsi
0x14001b14e  push    rdi
0x14001b14f  sub     rsp, 30h
0x14001b153  mov     rax, [rsp+38h+arg_20]
0x14001b158  mov     rbx, rcx
0x14001b15b  mov     [rcx+0A0h], rax
0x14001b162  mov     edi, r8d
0x14001b165  mov     rcx, [rcx+0A8h]; this
0x14001b16c  mov     rsi, rdx
0x14001b16f  test    rcx, rcx
0x14001b172  jz      short loc_14001B179
0x14001b174  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x14001b179  mov     rcx, [rsp+38h+arg_28]; this
0x14001b17e  mov     [rbx+0A8h], rcx
0x14001b185  test    rcx, rcx
0x14001b188  jz      short loc_14001B18F
0x14001b18a  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14001b18f  mov     eax, [rsp+38h+arg_38]
0x14001b193  lea     rcx, [rbx+18h]; Handle
0x14001b197  mov     [rbx+0B0h], eax
0x14001b19d  mov     r8d, edi; unsigned int
0x14001b1a0  mov     dword ptr [rbx+0B4h], 0
0x14001b1aa  mov     rdx, rsi; HANDLE
0x14001b1ad  test    eax, eax
0x14001b1af  jnz     short loc_14001B1C7
0x14001b1b1  mov     eax, [rsp+38h+arg_30]
0x14001b1b5  lea     r9, aRdpdr; "RDPDR"
0x14001b1bc  mov     [rsp+38h+var_18], eax; int
0x14001b1c0  call    ?CreateTermDD@@YAJPEAPEAXPEAXKPEBDH@Z; CreateTermDD(void * *,void *,ulong,char const *,int)
0x14001b1c5  jmp     short loc_14001B1CC
0x14001b1c7  call    ?ReferenceRdpExtensionChannel@@YAJPEAPEAXPEAXKPEBD@Z; ReferenceRdpExtensionChannel(void * *,void *,ulong,char const *)
0x14001b1cc  test    eax, eax
0x14001b1ce  js      short loc_14001B1D7
0x14001b1d0  mov     eax, 1
0x14001b1d5  jmp     short loc_14001B1F6
0x14001b1d7  mov     rcx, [rbx+0A0h]; Event
0x14001b1de  test    rcx, rcx
0x14001b1e1  jz      short loc_14001B1F4
0x14001b1e3  xor     r8d, r8d; Wait
0x14001b1e6  xor     edx, edx; Increment
0x14001b1e8  call    cs:__imp_KeSetEvent
0x14001b1ef  nop     dword ptr [rax+rax+00h]
0x14001b1f4  xor     eax, eax
0x14001b1f6  mov     rbx, [rsp+38h+arg_0]
0x14001b1fb  mov     rsi, [rsp+38h+arg_8]
0x14001b200  add     rsp, 30h
0x14001b204  pop     rdi
0x14001b205  retn
```
