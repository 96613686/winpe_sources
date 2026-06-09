# SendPending

- ea: `0x140017d90`
- end: `0x140017f99`
- name: `SendPending`
- size: `521`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x140003080`
- `0x140003a04`
- `0x14000447c`
- `0x14000f698`
- `0x140017d90`
- `0x14001c1b0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140017edd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017f7f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017edd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017f7f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017df7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140017df7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017e0a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017f58`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017e0a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017f58`
- `NDIS!NdisGetDataBuffer` at `0x140017eb8`
- `NDIS!NdisGetDataBuffer` at `0x140017eb8`

## pseudocode

```c
void __fastcall SendPending(PVOID Entry, __int64 a2)
{
  __int64 **v4; // rsi
  __int64 *i; // rdi
  int v6; // eax
  char v7; // r14
  __int64 v8; // rdx
  __int64 v9; // rax
  unsigned int v10; // eax
  __int64 AlignOffset; // [rsp+20h] [rbp-48h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_dd(
      WPP_GLOBAL_Control->AttachedDevice,
      18,
      WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids,
      *(unsigned int *)(a2 + 224),
      *(_DWORD *)(a2 + 228));
  }
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a2 + 24) + 960LL), Entry);
  *(_BYTE *)(a2 + 40) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
  if ( *(_DWORD *)(a2 + 224) < *(_DWORD *)(a2 + 228) )
  {
    v4 = (__int64 **)(a2 + 208);
LABEL_7:
    for ( i = *v4; i != (__int64 *)v4; i = (__int64 *)*i )
    {
      v6 = *((_DWORD *)i + 9);
      if ( (v6 & 1) != 0 )
      {
        v7 = *((_DWORD *)i + 9);
        *((_DWORD *)i + 9) = v6 & 0xFFFFFFBE;
        ++*(_DWORD *)(a2 + 224);
        v8 = *(_QWORD *)(a2 + 256);
        if ( v8 )
        {
          RemoveTqi(*(_QWORD *)(a2 + 304), v8, 1);
          *(_QWORD *)(a2 + 256) = 0;
        }
        if ( *((_DWORD *)i + 8) )
          *((_WORD *)NdisGetDataBuffer(*(PNET_BUFFER *)(i[5] + 8), *(_DWORD *)(*(_QWORD *)(i[5] + 8) + 24LL), 0, 1u, 0)
          + 5) = __ROR2__(*(_WORD *)(a2 + 280), 8);
        else
          i[8] = MEMORY[0xFFFFF78000000014];
        _InterlockedIncrement((volatile signed __int32 *)i + 4);
        KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 32), *(_BYTE *)(a2 + 40));
        if ( (v7 & 0x40) != 0 )
          NsiCliGetInterfaceSpeed(*(unsigned int *)(a2 + 108), a2 + 376);
        v9 = i[5];
        AlignOffset = *(_QWORD *)(v9 + 8);
        *(_QWORD *)(AlignOffset + 128) = v9;
        v10 = L2tpSendDatagram(a2, (_DWORD)i, AlignOffset, 1, AlignOffset);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids, v10);
        }
        *(_BYTE *)(a2 + 40) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
        if ( *(_DWORD *)(a2 + 224) < *(_DWORD *)(a2 + 228) )
          goto LABEL_7;
        break;
      }
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 32), *(_BYTE *)(a2 + 40));
}

```

## disassembly

```asm
0x140017d90  push    rbx
0x140017d92  push    rbp
0x140017d93  push    rsi
0x140017d94  push    rdi
0x140017d95  push    r13
0x140017d97  push    r14
0x140017d99  sub     rsp, 38h
0x140017d9d  mov     rbx, rdx
0x140017da0  mov     rdi, rcx
0x140017da3  mov     rcx, cs:WPP_GLOBAL_Control
0x140017daa  lea     r13, WPP_GLOBAL_Control
0x140017db1  cmp     rcx, r13
0x140017db4  jz      short loc_140017DE9
0x140017db6  mov     eax, [rcx+2Ch]
0x140017db9  test    al, 10h
0x140017dbb  jz      short loc_140017DE9
0x140017dbd  cmp     byte ptr [rcx+29h], 1
0x140017dc1  jb      short loc_140017DE9
0x140017dc3  mov     eax, [rbx+0E4h]
0x140017dc9  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x140017dd0  mov     r9d, [rbx+0E0h]
0x140017dd7  mov     edx, 12h
0x140017ddc  mov     rcx, [rcx+18h]
0x140017de0  mov     [rsp+68h+AlignOffset], eax
0x140017de4  call    WPP_SF_dd
0x140017de9  mov     rcx, [rbx+18h]
0x140017ded  mov     rdx, rdi; Entry
0x140017df0  add     rcx, 3C0h; Lookaside
0x140017df7  call    cs:__imp_ExFreeToNPagedLookasideList
0x140017dfe  nop     dword ptr [rax+rax+00h]
0x140017e03  lea     rbp, [rbx+20h]
0x140017e07  mov     rcx, rbp; SpinLock
0x140017e0a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017e11  nop     dword ptr [rax+rax+00h]
0x140017e16  mov     [rbx+28h], al
0x140017e19  mov     eax, [rbx+0E4h]
0x140017e1f  cmp     [rbx+0E0h], eax
0x140017e25  jnb     loc_140017F79
0x140017e2b  lea     rsi, [rbx+0D0h]
0x140017e32  mov     rdi, [rsi]
0x140017e35  jmp     short loc_140017E41
0x140017e37  mov     eax, [rdi+24h]
0x140017e3a  test    al, 1
0x140017e3c  jnz     short loc_140017E4B
0x140017e3e  mov     rdi, [rdi]
0x140017e41  cmp     rdi, rsi
0x140017e44  jnz     short loc_140017E37
0x140017e46  jmp     loc_140017F79
0x140017e4b  mov     r14d, eax
0x140017e4e  and     eax, 0FFFFFFBEh
0x140017e51  mov     [rdi+24h], eax
0x140017e54  inc     dword ptr [rbx+0E0h]
0x140017e5a  mov     rdx, [rbx+100h]
0x140017e61  test    rdx, rdx
0x140017e64  jz      short loc_140017E83
0x140017e66  mov     rcx, [rbx+130h]
0x140017e6d  mov     r8d, 1
0x140017e73  call    RemoveTqi
0x140017e78  mov     qword ptr [rbx+100h], 0
0x140017e83  cmp     dword ptr [rdi+20h], 0
0x140017e87  jnz     short loc_140017E9C
0x140017e89  mov     rax, 0FFFFF78000000014h
0x140017e93  mov     rax, [rax]
0x140017e96  mov     [rdi+40h], rax
0x140017e9a  jmp     short loc_140017ED3
0x140017e9c  mov     rax, [rdi+28h]
0x140017ea0  mov     r9d, 1; AlignMultiple
0x140017ea6  xor     r8d, r8d; Storage
0x140017ea9  mov     [rsp+68h+AlignOffset], 0; AlignOffset
0x140017eb1  mov     rcx, [rax+8]; NetBuffer
0x140017eb5  mov     edx, [rcx+18h]; BytesNeeded
0x140017eb8  call    cs:__imp_NdisGetDataBuffer
0x140017ebf  nop     dword ptr [rax+rax+00h]
0x140017ec4  movzx   ecx, word ptr [rbx+118h]
0x140017ecb  ror     cx, 8
0x140017ecf  mov     [rax+0Ah], cx
0x140017ed3  lock inc dword ptr [rdi+10h]
0x140017ed7  mov     dl, [rbx+28h]; NewIrql
0x140017eda  mov     rcx, rbp; SpinLock
0x140017edd  call    cs:__imp_KeReleaseSpinLock
0x140017ee4  nop     dword ptr [rax+rax+00h]
0x140017ee9  test    r14b, 40h
0x140017eed  jz      short loc_140017EFE
0x140017eef  mov     ecx, [rbx+6Ch]
0x140017ef2  lea     rdx, [rbx+178h]
0x140017ef9  call    NsiCliGetInterfaceSpeed
0x140017efe  mov     rax, [rdi+28h]
0x140017f02  mov     r9d, 1
0x140017f08  mov     rdx, rdi
0x140017f0b  mov     rcx, rbx
0x140017f0e  mov     r8, [rax+8]
0x140017f12  mov     qword ptr [rsp+68h+AlignOffset], r8
0x140017f17  mov     [r8+80h], rax
0x140017f1e  call    L2tpSendDatagram
0x140017f23  mov     rcx, cs:WPP_GLOBAL_Control
0x140017f2a  cmp     rcx, r13
0x140017f2d  jz      short loc_140017F55
0x140017f2f  mov     edx, [rcx+2Ch]
0x140017f32  test    dl, 10h
0x140017f35  jz      short loc_140017F55
0x140017f37  cmp     byte ptr [rcx+29h], 4
0x140017f3b  jb      short loc_140017F55
0x140017f3d  mov     rcx, [rcx+18h]
0x140017f41  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x140017f48  mov     edx, 13h
0x140017f4d  mov     r9d, eax
0x140017f50  call    WPP_SF_d
0x140017f55  mov     rcx, rbp; SpinLock
0x140017f58  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017f5f  nop     dword ptr [rax+rax+00h]
0x140017f64  mov     [rbx+28h], al
0x140017f67  mov     eax, [rbx+0E4h]
0x140017f6d  cmp     [rbx+0E0h], eax
0x140017f73  jb      loc_140017E32
0x140017f79  mov     dl, [rbx+28h]; NewIrql
0x140017f7c  mov     rcx, rbp; SpinLock
0x140017f7f  call    cs:__imp_KeReleaseSpinLock
0x140017f86  nop     dword ptr [rax+rax+00h]
0x140017f8b  add     rsp, 38h
0x140017f8f  pop     r14
0x140017f91  pop     r13
0x140017f93  pop     rdi
0x140017f94  pop     rsi
0x140017f95  pop     rbp
0x140017f96  pop     rbx
0x140017f97  retn
```
