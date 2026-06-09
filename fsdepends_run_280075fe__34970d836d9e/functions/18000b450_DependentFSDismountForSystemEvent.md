# DependentFSDismountForSystemEvent

- ea: `0x18000b450`
- end: `0x18000b5e8`
- name: `DependentFSDismountForSystemEvent`
- size: `408`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001020`
- `0x180001460`
- `0x18000aecc`
- `0x18000b450`
- `0x18000eac0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000b596`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000b596`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000b572`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000b572`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000b58a`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000b58a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000b49a`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x18000b49a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000b481`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000b481`

## pseudocode

```c
__int64 __fastcall DependentFSDismountForSystemEvent(unsigned int a1)
{
  unsigned int v2; // ebx
  char v3; // di
  int v4; // eax
  PVOID P; // [rsp+68h] [rbp+10h] BYREF

  P = 0;
  if ( byte_180005194 || byte_180005196 )
    return 0;
  v2 = 0;
  KeEnterCriticalRegion();
  v3 = 1;
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids, a1);
  }
  if ( byte_180005194 || byte_180005196 || !dword_180005180 )
  {
LABEL_17:
    if ( P )
      ExFreePoolWithTag(P, 0x6C447044u);
    if ( !v3 )
      goto LABEL_21;
    goto LABEL_20;
  }
  v4 = DepFSGenerateDependencyList(0, 0, a1, &P, 1, 256);
  v2 = v4;
  if ( v4 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids, (unsigned int)v4);
  }
  if ( P )
  {
    v2 = DepFSDismountDependencyList((__int64)P, 0, 1);
    v3 = 0;
    goto LABEL_17;
  }
LABEL_20:
  ExReleaseResourceLite(&Resource);
  KeLeaveCriticalRegion();
LABEL_21:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_DD(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids, a1, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x18000b450  push    rbx
0x18000b452  push    rsi
0x18000b453  push    rdi
0x18000b454  push    r14
0x18000b456  sub     rsp, 38h
0x18000b45a  cmp     cs:byte_180005194, 0
0x18000b461  mov     esi, ecx
0x18000b463  mov     [rsp+58h+P], 0
0x18000b46c  jnz     loc_18000B5DB
0x18000b472  cmp     cs:byte_180005196, 0
0x18000b479  jnz     loc_18000B5DB
0x18000b47f  xor     ebx, ebx
0x18000b481  call    cs:__imp_KeEnterCriticalRegion
0x18000b488  nop     dword ptr [rax+rax+00h]
0x18000b48d  mov     dil, 1
0x18000b490  lea     rcx, Resource; Resource
0x18000b497  mov     dl, dil; Wait
0x18000b49a  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000b4a1  nop     dword ptr [rax+rax+00h]
0x18000b4a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b4ad  lea     r14, WPP_GLOBAL_Control
0x18000b4b4  cmp     rcx, r14
0x18000b4b7  jz      short loc_18000B4DC
0x18000b4b9  mov     eax, [rcx+2Ch]
0x18000b4bc  test    al, 10h
0x18000b4be  jz      short loc_18000B4DC
0x18000b4c0  cmp     byte ptr [rcx+29h], 4
0x18000b4c4  jb      short loc_18000B4DC
0x18000b4c6  mov     rcx, [rcx+18h]
0x18000b4ca  lea     edx, [rbx+1Bh]
0x18000b4cd  mov     r9d, esi
0x18000b4d0  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000b4d7  call    WPP_SF_D
0x18000b4dc  cmp     cs:byte_180005194, bl
0x18000b4e2  jnz     short loc_18000B563
0x18000b4e4  cmp     cs:byte_180005196, bl
0x18000b4ea  jnz     short loc_18000B563
0x18000b4ec  cmp     cs:dword_180005180, ebx
0x18000b4f2  jz      short loc_18000B563
0x18000b4f4  mov     [rsp+58h+var_30], 100h
0x18000b4fc  lea     r9, [rsp+58h+P]
0x18000b501  mov     r8d, esi
0x18000b504  mov     byte ptr [rsp+58h+var_38], dil
0x18000b509  xor     edx, edx
0x18000b50b  xor     ecx, ecx
0x18000b50d  call    DepFSGenerateDependencyList
0x18000b512  mov     ebx, eax
0x18000b514  test    eax, eax
0x18000b516  jns     short loc_18000B54A
0x18000b518  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b51f  cmp     rcx, r14
0x18000b522  jz      short loc_18000B54A
0x18000b524  mov     edx, [rcx+2Ch]
0x18000b527  test    dil, dl
0x18000b52a  jz      short loc_18000B54A
0x18000b52c  cmp     byte ptr [rcx+29h], 2
0x18000b530  jb      short loc_18000B54A
0x18000b532  mov     rcx, [rcx+18h]
0x18000b536  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000b53d  mov     edx, 1Ch
0x18000b542  mov     r9d, eax
0x18000b545  call    WPP_SF_D
0x18000b54a  mov     rcx, [rsp+58h+P]
0x18000b54f  test    rcx, rcx
0x18000b552  jz      short loc_18000B583
0x18000b554  mov     r8b, dil
0x18000b557  xor     edx, edx
0x18000b559  call    DepFSDismountDependencyList
0x18000b55e  mov     ebx, eax
0x18000b560  xor     dil, dil
0x18000b563  mov     rcx, [rsp+58h+P]; P
0x18000b568  test    rcx, rcx
0x18000b56b  jz      short loc_18000B57E
0x18000b56d  mov     edx, 6C447044h; Tag
0x18000b572  call    cs:__imp_ExFreePoolWithTag
0x18000b579  nop     dword ptr [rax+rax+00h]
0x18000b57e  test    dil, dil
0x18000b581  jz      short loc_18000B5A2
0x18000b583  lea     rcx, Resource; Resource
0x18000b58a  call    cs:__imp_ExReleaseResourceLite
0x18000b591  nop     dword ptr [rax+rax+00h]
0x18000b596  call    cs:__imp_KeLeaveCriticalRegion
0x18000b59d  nop     dword ptr [rax+rax+00h]
0x18000b5a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b5a9  cmp     rcx, r14
0x18000b5ac  jz      short loc_18000B5D7
0x18000b5ae  mov     eax, [rcx+2Ch]
0x18000b5b1  test    al, 10h
0x18000b5b3  jz      short loc_18000B5D7
0x18000b5b5  cmp     byte ptr [rcx+29h], 4
0x18000b5b9  jb      short loc_18000B5D7
0x18000b5bb  mov     rcx, [rcx+18h]
0x18000b5bf  lea     r8, WPP_b2ba12f3bc77374238ec5953d8d4ec6b_Traceguids
0x18000b5c6  mov     edx, 1Dh
0x18000b5cb  mov     [rsp+58h+var_38], ebx
0x18000b5cf  mov     r9d, esi
0x18000b5d2  call    WPP_SF_DD
0x18000b5d7  mov     eax, ebx
0x18000b5d9  jmp     short loc_18000B5DD
0x18000b5db  xor     eax, eax
0x18000b5dd  add     rsp, 38h
0x18000b5e1  pop     r14
0x18000b5e3  pop     rdi
0x18000b5e4  pop     rsi
0x18000b5e5  pop     rbx
0x18000b5e6  retn
```
