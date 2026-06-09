# RxAcquireFcbForModWrite

- ea: `0x140008e50`
- end: `0x140008f55`
- name: `RxAcquireFcbForModWrite`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140008e50`
- `0x140008f60`
- `0x14000bbf0`
- `0x14000e770`
- `0x140016e70`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140008f44`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140008f44`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140008ec5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140008ec5`

## pseudocode

```c
__int64 __fastcall RxAcquireFcbForModWrite(__int64 a1, _QWORD *a2, struct _ERESOURCE **a3)
{
  __int64 v3; // rbx
  char v6; // si
  char v7; // al
  __int64 v8; // rax
  struct _ERESOURCE *v9; // rdi
  BOOLEAN v10; // al
  __int64 v12; // [rsp+60h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 24);
  LOBYTE(v12) = 1;
  v6 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 41, &WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v3);
  }
  if ( *(_QWORD *)(v3 + 128) )
  {
    v7 = RxWaitForStableLViewOnFcbAndAcquireRundown(0, (PMRX_FCB)v3, 1u, 0, &v12);
    if ( !(_BYTE)v12 )
    {
      if ( !v7 )
        return 3221225688LL;
      v6 = 1;
    }
  }
  v8 = *(_QWORD *)(v3 + 40);
  if ( *a2 <= v8 || v8 == *(_QWORD *)(v3 + 32) )
  {
    v9 = *(struct _ERESOURCE **)(v3 + 16);
    v10 = ExAcquireResourceSharedLite(v9, 0);
  }
  else
  {
    v9 = *(struct _ERESOURCE **)(v3 + 8);
    RxPurgeTurboIoCache(v3, 1);
    v10 = ExAcquireResourceExclusiveLite(v9, 0);
  }
  if ( v10 )
  {
    *a3 = v9;
    return 0;
  }
  if ( v6 )
    RxReleaseRundownDerefView(v3);
  return 3221225688LL;
}

```

## disassembly

```asm
0x140008e50  push    rbx
0x140008e52  push    rsi
0x140008e53  push    rdi
0x140008e54  push    r14
0x140008e56  sub     rsp, 38h
0x140008e5a  mov     rbx, [rcx+18h]
0x140008e5e  mov     r14, r8
0x140008e61  mov     rdi, rdx
0x140008e64  mov     byte ptr [rsp+58h+arg_0], 1
0x140008e69  xor     sil, sil
0x140008e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e73  lea     rax, WPP_GLOBAL_Control
0x140008e7a  cmp     rcx, rax
0x140008e7d  jz      short loc_140008E88
0x140008e7f  test    dword ptr [rcx+2Ch], 100h
0x140008e86  jnz     short loc_140008F04
0x140008e88  cmp     qword ptr [rbx+80h], 0
0x140008e90  jz      short loc_140008EB3
0x140008e92  lea     rax, [rsp+58h+arg_0]
0x140008e97  xor     r9d, r9d
0x140008e9a  mov     r8b, 1
0x140008e9d  mov     [rsp+58h+var_38], rax; __int64
0x140008ea2  mov     rdx, rbx; MrxFcb
0x140008ea5  xor     ecx, ecx; Condition
0x140008ea7  call    RxWaitForStableLViewOnFcbAndAcquireRundown
0x140008eac  cmp     byte ptr [rsp+58h+arg_0], sil
0x140008eb1  jz      short loc_140008EDC
0x140008eb3  mov     rax, [rbx+28h]
0x140008eb7  cmp     [rdi], rax
0x140008eba  jg      short loc_140008F2B
0x140008ebc  mov     rdi, [rbx+10h]
0x140008ec0  xor     edx, edx; Wait
0x140008ec2  mov     rcx, rdi; Resource
0x140008ec5  call    cs:__imp_ExAcquireResourceSharedLite
0x140008ecc  nop     dword ptr [rax+rax+00h]
0x140008ed1  test    al, al
0x140008ed3  jz      short loc_140008EF0
0x140008ed5  mov     [r14], rdi
0x140008ed8  xor     eax, eax
0x140008eda  jmp     short loc_140008EE5
0x140008edc  test    al, al
0x140008ede  jnz     short loc_140008EFF
0x140008ee0  mov     eax, 0C00000D8h
0x140008ee5  add     rsp, 38h
0x140008ee9  pop     r14
0x140008eeb  pop     rdi
0x140008eec  pop     rsi
0x140008eed  pop     rbx
0x140008eee  retn
0x140008ef0  test    sil, sil
0x140008ef3  jz      short loc_140008EE0
0x140008ef5  mov     rcx, rbx
0x140008ef8  call    RxReleaseRundownDerefView
0x140008efd  jmp     short loc_140008EE0
0x140008eff  mov     sil, 1
0x140008f02  jmp     short loc_140008EB3
0x140008f04  cmp     byte ptr [rcx+29h], 2
0x140008f08  jb      loc_140008E88
0x140008f0e  mov     rcx, [rcx+18h]
0x140008f12  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x140008f19  mov     edx, 29h ; ')'
0x140008f1e  mov     r9, rbx
0x140008f21  call    WPP_SF_q
0x140008f26  jmp     loc_140008E88
0x140008f2b  cmp     rax, [rbx+20h]
0x140008f2f  jz      short loc_140008EBC
0x140008f31  mov     rdi, [rbx+8]
0x140008f35  mov     dl, 1
0x140008f37  mov     rcx, rbx
0x140008f3a  call    RxPurgeTurboIoCache
0x140008f3f  xor     edx, edx; Wait
0x140008f41  mov     rcx, rdi; Resource
0x140008f44  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140008f4b  nop     dword ptr [rax+rax+00h]
0x140008f50  jmp     loc_140008ED1
```
