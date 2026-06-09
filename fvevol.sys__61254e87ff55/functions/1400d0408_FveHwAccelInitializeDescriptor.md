# FveHwAccelInitializeDescriptor

- ea: `0x1400d0408`
- end: `0x1400d055f`
- name: `FveHwAccelInitializeDescriptor`
- size: `343`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400d0568`
- `0x1400d1b04`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x140023040`
- `0x1400d0408`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400d046d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400d046d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400d0507`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400d0507`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d047d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d0513`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d047d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d0513`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d0458`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d0458`
- `ext-ms-win-accel-api-km-l1-1-1!AccelInitializeDescriptor` at `0x1400d04b6`
- `ext-ms-win-accel-api-km-l1-1-1!AccelInitializeDescriptor` at `0x1400d04b6`

## pseudocode

```c
__int64 __fastcall FveHwAccelInitializeDescriptor(__int64 a1, char a2, void *a3)
{
  __int64 v3; // rdi
  __int64 v6; // rdx
  unsigned int v7; // ebx
  int v8; // eax

  v3 = *(_QWORD *)(a1 + 8);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 113, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids);
  }
  if ( a2 )
  {
    KeEnterCriticalRegion();
    if ( !ExAcquireResourceSharedLite((PERESOURCE)(v3 + 10600), 1u) )
      KeLeaveCriticalRegion();
  }
  v6 = *(unsigned int *)(v3 + 10744);
  if ( (*(_DWORD *)(v3 + 9928) & 0x800000) != 0 )
  {
    memset(a3, 0, (unsigned int)v6);
    v7 = 0;
  }
  else
  {
    v8 = AccelInitializeDescriptor(*(_QWORD *)(v3 + 10736), v6, a3);
    v7 = v8;
    if ( v8 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        114,
        WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
        (unsigned int)v8);
    }
  }
  if ( a2 )
  {
    ExReleaseResourceLite((PERESOURCE)(v3 + 10600));
    KeLeaveCriticalRegion();
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 115, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, v7);
  }
  return v7;
}

```

## disassembly

```asm
0x1400d0408  push    rbx
0x1400d040a  push    rsi
0x1400d040b  push    rdi
0x1400d040c  push    r14
0x1400d040e  sub     rsp, 28h
0x1400d0412  mov     rdi, [rcx+8]
0x1400d0416  mov     rbx, r8
0x1400d0419  mov     sil, dl
0x1400d041c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d0423  lea     r14, WPP_GLOBAL_Control
0x1400d042a  cmp     rcx, r14
0x1400d042d  jz      short loc_1400D0453
0x1400d042f  test    dword ptr [rcx+2Ch], 400000h
0x1400d0436  jz      short loc_1400D0453
0x1400d0438  cmp     byte ptr [rcx+29h], 5
0x1400d043c  jb      short loc_1400D0453
0x1400d043e  mov     rcx, [rcx+18h]
0x1400d0442  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400d0449  mov     edx, 71h ; 'q'
0x1400d044e  call    WPP_SF_
0x1400d0453  test    sil, sil
0x1400d0456  jz      short loc_1400D0489
0x1400d0458  call    cs:__imp_KeEnterCriticalRegion
0x1400d045f  nop     dword ptr [rax+rax+00h]
0x1400d0464  lea     rcx, [rdi+2968h]; Resource
0x1400d046b  mov     dl, 1; Wait
0x1400d046d  call    cs:__imp_ExAcquireResourceSharedLite
0x1400d0474  nop     dword ptr [rax+rax+00h]
0x1400d0479  test    al, al
0x1400d047b  jnz     short loc_1400D0489
0x1400d047d  call    cs:__imp_KeLeaveCriticalRegion
0x1400d0484  nop     dword ptr [rax+rax+00h]
0x1400d0489  test    dword ptr [rdi+26C8h], 800000h
0x1400d0493  mov     edx, [rdi+29F8h]
0x1400d0499  jz      short loc_1400D04AC
0x1400d049b  mov     r8d, edx; Size
0x1400d049e  mov     rcx, rbx; void *
0x1400d04a1  xor     edx, edx; Val
0x1400d04a3  call    memset
0x1400d04a8  xor     ebx, ebx
0x1400d04aa  jmp     short loc_1400D04FB
0x1400d04ac  mov     rcx, [rdi+29F0h]
0x1400d04b3  mov     r8, rbx
0x1400d04b6  call    cs:__imp_AccelInitializeDescriptor
0x1400d04bd  nop     dword ptr [rax+rax+00h]
0x1400d04c2  mov     ebx, eax
0x1400d04c4  test    eax, eax
0x1400d04c6  jns     short loc_1400D04FB
0x1400d04c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d04cf  cmp     rcx, r14
0x1400d04d2  jz      short loc_1400D04FB
0x1400d04d4  test    dword ptr [rcx+2Ch], 400000h
0x1400d04db  jz      short loc_1400D04FB
0x1400d04dd  cmp     byte ptr [rcx+29h], 2
0x1400d04e1  jb      short loc_1400D04FB
0x1400d04e3  mov     rcx, [rcx+18h]
0x1400d04e7  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400d04ee  mov     edx, 72h ; 'r'
0x1400d04f3  mov     r9d, eax
0x1400d04f6  call    WPP_SF_d
0x1400d04fb  test    sil, sil
0x1400d04fe  jz      short loc_1400D051F
0x1400d0500  lea     rcx, [rdi+2968h]; Resource
0x1400d0507  call    cs:__imp_ExReleaseResourceLite
0x1400d050e  nop     dword ptr [rax+rax+00h]
0x1400d0513  call    cs:__imp_KeLeaveCriticalRegion
0x1400d051a  nop     dword ptr [rax+rax+00h]
0x1400d051f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d0526  cmp     rcx, r14
0x1400d0529  jz      short loc_1400D0552
0x1400d052b  test    dword ptr [rcx+2Ch], 400000h
0x1400d0532  jz      short loc_1400D0552
0x1400d0534  cmp     byte ptr [rcx+29h], 5
0x1400d0538  jb      short loc_1400D0552
0x1400d053a  mov     rcx, [rcx+18h]
0x1400d053e  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400d0545  mov     edx, 73h ; 's'
0x1400d054a  mov     r9d, ebx
0x1400d054d  call    WPP_SF_d
0x1400d0552  mov     eax, ebx
0x1400d0554  add     rsp, 28h
0x1400d0558  pop     r14
0x1400d055a  pop     rdi
0x1400d055b  pop     rsi
0x1400d055c  pop     rbx
0x1400d055d  retn
```
