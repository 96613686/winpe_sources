# ACpCreateHeap(_DEVICE_OBJECT *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x14000f204`
- end: `0x14000f2ab`
- name: `?ACpCreateHeap@@YAPEAXPEAU_DEVICE_OBJECT@@PEB_W111@Z`
- size: `167`
- prototype: `void *__fastcall(struct _DEVICE_OBJECT *, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14000bb00`

## callees

- `0x140001128`
- `0x140001c04`
- `0x14000ed80`
- `0x14000f204`

## pseudocode

```c
void *__fastcall ACpCreateHeap(
        struct _DEVICE_OBJECT *a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        wchar_t *a5)
{
  _QWORD *DeviceExtension; // rbx
  CSMAllocator *v10; // rax

  DeviceExtension = a1->DeviceExtension;
  v10 = (CSMAllocator *)operator new(0xD8u, 0x100u, 0x4841514Du, LowPoolPriority);
  if ( v10 )
    v10 = CSMAllocator::CSMAllocator(v10, a1, a2, a3, a4, a5);
  DeviceExtension[40] = v10;
  if ( !v10
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 45, &WPP_664e97eed756311217f592c2f10907d7_Traceguids);
  }
  return (void *)DeviceExtension[40];
}

```

## disassembly

```asm
0x14000f204  push    rbx
0x14000f206  push    rbp
0x14000f207  push    rsi
0x14000f208  push    rdi
0x14000f209  push    r14
0x14000f20b  sub     rsp, 30h
0x14000f20f  mov     rbx, [rcx+40h]
0x14000f213  mov     r14, rdx
0x14000f216  mov     edx, 100h; unsigned __int64
0x14000f21b  mov     rsi, r9
0x14000f21e  mov     rbp, r8
0x14000f221  mov     rdi, rcx
0x14000f224  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000f227  mov     r8d, 4841514Dh; unsigned int
0x14000f22d  lea     ecx, [rdx-28h]; unsigned __int64
0x14000f230  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000f235  test    rax, rax
0x14000f238  jz      short loc_14000F25D
0x14000f23a  mov     r8, [rsp+58h+arg_20]
0x14000f242  mov     r9, rbp; wchar_t *
0x14000f245  mov     [rsp+58h+var_30], r8; wchar_t *
0x14000f24a  mov     rdx, rdi; struct _DEVICE_OBJECT *
0x14000f24d  mov     r8, r14; wchar_t *
0x14000f250  mov     [rsp+58h+var_38], rsi; wchar_t *
0x14000f255  mov     rcx, rax; this
0x14000f258  call    ??0CSMAllocator@@QEAA@PEAU_DEVICE_OBJECT@@PEB_W111@Z; CSMAllocator::CSMAllocator(_DEVICE_OBJECT *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)
0x14000f25d  mov     [rbx+140h], rax
0x14000f264  test    rax, rax
0x14000f267  jnz     short loc_14000F298
0x14000f269  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f270  lea     rax, WPP_GLOBAL_Control
0x14000f277  cmp     rcx, rax
0x14000f27a  jz      short loc_14000F298
0x14000f27c  mov     eax, [rcx+6Ch]
0x14000f27f  test    al, 1
0x14000f281  jz      short loc_14000F298
0x14000f283  mov     rcx, [rcx+58h]
0x14000f287  lea     r8, WPP_664e97eed756311217f592c2f10907d7_Traceguids
0x14000f28e  mov     edx, 2Dh ; '-'
0x14000f293  call    WPP_SF_
0x14000f298  mov     rax, [rbx+140h]
0x14000f29f  add     rsp, 30h
0x14000f2a3  pop     r14
0x14000f2a5  pop     rdi
0x14000f2a6  pop     rsi
0x14000f2a7  pop     rbp
0x14000f2a8  pop     rbx
0x14000f2a9  retn
```
