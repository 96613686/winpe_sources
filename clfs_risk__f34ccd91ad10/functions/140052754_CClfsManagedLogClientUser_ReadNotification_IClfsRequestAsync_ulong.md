# CClfsManagedLogClientUser::ReadNotification(IClfsRequestAsync *,ulong *)

- ea: `0x140052754`
- end: `0x1400528af`
- name: `?ReadNotification@CClfsManagedLogClientUser@@QEAAJPEAUIClfsRequestAsync@@PEAK@Z`
- size: `347`
- prototype: `__int64 __fastcall(CClfsManagedLogClientUser *__hidden this, struct IClfsRequestAsync *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140050434`

## callees

- `0x140017f20`
- `0x140051fb8`
- `0x140052754`

## import_xrefs

- `ntoskrnl!KeRemoveQueue` at `0x1400527d9`
- `ntoskrnl!KeRemoveQueue` at `0x1400527d9`
- `ntoskrnl!KeReadStateQueue` at `0x1400527a6`
- `ntoskrnl!KeReadStateQueue` at `0x1400527a6`

## pseudocode

```c
__int64 __fastcall CClfsManagedLogClientUser::ReadNotification(
        CClfsManagedLogClientUser *this,
        struct IClfsRequestAsync *a2,
        unsigned int *a3)
{
  PRKQUEUE *v6; // rcx
  int v7; // ebx
  PLIST_ENTRY v8; // rsi
  struct _LIST_ENTRY *v9; // rcx
  LARGE_INTEGER Timeout; // [rsp+68h] [rbp+20h] BYREF

  *a3 = 0;
  (*(void (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a2 + 32LL))(a2);
  v6 = (PRKQUEUE *)*((_QWORD *)this + 28);
  if ( v6 )
  {
    if ( KeReadStateQueue(*v6)
      && (Timeout.QuadPart = 0, (v8 = KeRemoveQueue(**((PRKQUEUE **)this + 28), 0, &Timeout)) != 0) )
    {
      v9 = *(struct _LIST_ENTRY **)((*(__int64 (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a2 + 32LL))(a2)
                                  + 24);
      *v9 = *(PLIST_ENTRY)((char *)v8 + 24);
      v9[1].Flink = v8[2].Blink;
      CClfsManagedLogClientUser::DestroyNotification(this, (struct CClfsManagedLogClientUser::_NOTIFICATION_PACKET *)v8);
      *a3 = 24;
      v7 = 0;
    }
    else
    {
      (**(void (__fastcall ***)(struct IClfsRequestAsync *))a2)(a2);
      (*(void (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a2 + 120LL))(a2);
      v7 = (*(__int64 (__fastcall **)(_QWORD, struct IClfsRequestAsync *))(**(_QWORD **)(*((_QWORD *)this + 28) + 16LL)
                                                                         + 16LL))(
             *(_QWORD *)(*((_QWORD *)this + 28) + 16LL),
             a2);
      if ( v7 >= 0 )
        v7 = 259;
      else
        (*(void (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a2 + 8LL))(a2);
    }
  }
  else
  {
    v7 = -1073741436;
  }
  if ( v7 != 259 )
    (*(void (__fastcall **)(struct IClfsRequestAsync *, _QWORD))(*(_QWORD *)a2 + 128LL))(a2, (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140052754  mov     [rsp+arg_0], rbx
0x140052759  mov     [rsp+arg_8], rdx
0x14005275e  push    rsi
0x14005275f  push    rdi
0x140052760  push    r14
0x140052762  sub     rsp, 30h
0x140052766  mov     r14, r8
0x140052769  mov     rdi, rdx
0x14005276c  mov     rbx, rcx
0x14005276f  mov     [rsp+48h+var_28], 0
0x140052777  mov     dword ptr [r8], 0
0x14005277e  mov     rax, [rdx]
0x140052781  mov     rax, [rax+20h]
0x140052785  mov     rcx, rdx
0x140052788  call    _guard_dispatch_icall
0x14005278d  mov     rcx, [rbx+0E0h]
0x140052794  test    rcx, rcx
0x140052797  jnz     short loc_1400527A3
0x140052799  mov     ebx, 0C0000184h
0x14005279e  jmp     loc_14005287E
0x1400527a3  mov     rcx, [rcx]; Queue
0x1400527a6  call    cs:__imp_KeReadStateQueue
0x1400527ad  nop     dword ptr [rax+rax+00h]
0x1400527b2  test    eax, eax
0x1400527b4  jz      short loc_140052827
0x1400527b6  mov     qword ptr [rsp+48h+Timeout], 0
0x1400527bf  mov     qword ptr [rsp+48h+Timeout], 0
0x1400527c8  mov     rcx, [rbx+0E0h]
0x1400527cf  lea     r8, [rsp+48h+Timeout]; Timeout
0x1400527d4  xor     edx, edx; WaitMode
0x1400527d6  mov     rcx, [rcx]; Queue
0x1400527d9  call    cs:__imp_KeRemoveQueue
0x1400527e0  nop     dword ptr [rax+rax+00h]
0x1400527e5  mov     rsi, rax
0x1400527e8  test    rax, rax
0x1400527eb  jz      short loc_140052827
0x1400527ed  mov     rcx, [rdi]
0x1400527f0  mov     rax, [rcx+20h]
0x1400527f4  mov     rcx, rdi
0x1400527f7  call    _guard_dispatch_icall
0x1400527fc  mov     rcx, [rax+18h]
0x140052800  movups  xmm0, xmmword ptr [rsi+18h]
0x140052804  movups  xmmword ptr [rcx], xmm0
0x140052807  movsd   xmm1, qword ptr [rsi+28h]
0x14005280c  movsd   qword ptr [rcx+10h], xmm1
0x140052811  mov     rdx, rsi; struct CClfsManagedLogClientUser::_NOTIFICATION_PACKET *
0x140052814  mov     rcx, rbx; this
0x140052817  call    ?DestroyNotification@CClfsManagedLogClientUser@@AEAAXPEAU_NOTIFICATION_PACKET@1@@Z; CClfsManagedLogClientUser::DestroyNotification(CClfsManagedLogClientUser::_NOTIFICATION_PACKET *)
0x14005281c  mov     dword ptr [r14], 18h
0x140052823  xor     ebx, ebx
0x140052825  jmp     short loc_14005287E
0x140052827  mov     rax, [rdi]
0x14005282a  mov     rax, [rax]
0x14005282d  mov     rcx, rdi
0x140052830  call    _guard_dispatch_icall
0x140052835  mov     rax, [rdi]
0x140052838  mov     rax, [rax+78h]
0x14005283c  mov     rcx, rdi
0x14005283f  call    _guard_dispatch_icall
0x140052844  mov     rax, [rbx+0E0h]
0x14005284b  mov     rcx, [rax+10h]
0x14005284f  mov     rax, [rcx]
0x140052852  mov     rax, [rax+10h]
0x140052856  mov     rdx, rdi
0x140052859  call    _guard_dispatch_icall
0x14005285e  mov     ebx, eax
0x140052860  mov     [rsp+48h+var_28], eax
0x140052864  test    eax, eax
0x140052866  jns     short loc_140052879
0x140052868  mov     rcx, [rdi]
0x14005286b  mov     rax, [rcx+8]
0x14005286f  mov     rcx, rdi
0x140052872  call    _guard_dispatch_icall
0x140052877  jmp     short loc_140052882
0x140052879  mov     ebx, 103h
0x14005287e  mov     [rsp+48h+var_28], ebx
0x140052882  cmp     ebx, 103h
0x140052888  jz      short loc_14005289E
0x14005288a  mov     rax, [rdi]
0x14005288d  mov     rax, [rax+80h]
0x140052894  mov     edx, ebx
0x140052896  mov     rcx, rdi
0x140052899  call    _guard_dispatch_icall
0x14005289e  mov     eax, ebx
0x1400528a0  mov     rbx, [rsp+48h+arg_0]
0x1400528a5  add     rsp, 30h
0x1400528a9  pop     r14
0x1400528ab  pop     rdi
0x1400528ac  pop     rsi
0x1400528ad  retn
0x140080b79  push    rbp
0x140080b7b  sub     rsp, 20h
0x140080b7f  mov     rbp, rdx
0x140080b82  mov     edx, [rbp+20h]
0x140080b85  cmp     edx, 103h
0x140080b8b  jz      short loc_140080BA1
0x140080b8d  mov     rcx, [rbp+58h]
0x140080b91  mov     rax, [rcx]
0x140080b94  mov     rax, [rax+80h]
0x140080b9b  call    _guard_dispatch_icall
0x140080ba0  nop
0x140080ba1  add     rsp, 20h
0x140080ba5  pop     rbp
0x140080ba6  retn
```
