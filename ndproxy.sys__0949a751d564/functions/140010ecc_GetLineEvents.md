# GetLineEvents

- ea: `0x140010ecc`
- end: `0x140010f5d`
- name: `GetLineEvents`
- size: `145`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140004ad0`

## callees

- `0x1400081c0`
- `0x140010ecc`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140010f3a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140010f3a`

## pseudocode

```c
__int64 __fastcall GetLineEvents(__int64 a1, unsigned int a2)
{
  unsigned int i; // edi
  char *DeviceExtension; // rbx
  __int64 v6; // rax

  for ( i = 0; ; i += 48 )
  {
    DeviceExtension = (char *)WPP_MAIN_CB.DeviceExtension;
    if ( WPP_MAIN_CB.DeviceExtension == &WPP_MAIN_CB.DeviceExtension || a2 < 0x30 )
      break;
    if ( *((struct _DEVICE_OBJECT **)WPP_MAIN_CB.DeviceExtension + 1) != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.DeviceExtension
      || (v6 = *(_QWORD *)WPP_MAIN_CB.DeviceExtension,
          *(PVOID *)(*(_QWORD *)WPP_MAIN_CB.DeviceExtension + 8LL) != WPP_MAIN_CB.DeviceExtension) )
    {
      __fastfail(3u);
    }
    WPP_MAIN_CB.DeviceExtension = *(PVOID *)WPP_MAIN_CB.DeviceExtension;
    *(_QWORD *)(v6 + 8) = &WPP_MAIN_CB.DeviceExtension;
    --LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink);
    memmove((void *)(a1 + i), DeviceExtension + 16, 0x30u);
    a2 -= 48;
    ExFreeToNPagedLookasideList(&ProviderEventLookaside, DeviceExtension);
  }
  return i;
}

```

## disassembly

```asm
0x140010ecc  push    rbx
0x140010ece  push    rbp
0x140010ecf  push    rsi
0x140010ed0  push    rdi
0x140010ed1  push    r14
0x140010ed3  sub     rsp, 20h
0x140010ed7  mov     esi, edx
0x140010ed9  lea     r14, WPP_MAIN_CB.DeviceExtension
0x140010ee0  mov     rbp, rcx
0x140010ee3  xor     edi, edi
0x140010ee5  mov     rbx, cs:WPP_MAIN_CB.DeviceExtension
0x140010eec  cmp     rbx, r14
0x140010eef  jz      short loc_140010F4F
0x140010ef1  cmp     esi, 30h ; '0'
0x140010ef4  jb      short loc_140010F4F
0x140010ef6  cmp     [rbx+8], r14
0x140010efa  jnz     short loc_140010F48
0x140010efc  mov     rax, [rbx]
0x140010eff  cmp     [rax+8], rbx
0x140010f03  jnz     short loc_140010F48
0x140010f05  mov     cs:WPP_MAIN_CB.DeviceExtension, rax
0x140010f0c  lea     rdx, [rbx+10h]; Src
0x140010f10  mov     [rax+8], r14
0x140010f14  mov     r8d, 30h ; '0'; Size
0x140010f1a  dec     dword ptr cs:WPP_MAIN_CB.Queue
0x140010f20  mov     ecx, edi
0x140010f22  add     rcx, rbp; void *
0x140010f25  call    memmove
0x140010f2a  mov     rdx, rbx; Entry
0x140010f2d  lea     rcx, ProviderEventLookaside; Lookaside
0x140010f34  add     edi, 30h ; '0'
0x140010f37  add     esi, 0FFFFFFD0h
0x140010f3a  call    cs:__imp_ExFreeToNPagedLookasideList
0x140010f41  nop     dword ptr [rax+rax+00h]
0x140010f46  jmp     short loc_140010EE5
0x140010f48  mov     ecx, 3
0x140010f4d  int     29h; Win8: RtlFailFast(ecx)
0x140010f4f  mov     eax, edi
0x140010f51  add     rsp, 20h
0x140010f55  pop     r14
0x140010f57  pop     rdi
0x140010f58  pop     rsi
0x140010f59  pop     rbp
0x140010f5a  pop     rbx
0x140010f5b  retn
```
