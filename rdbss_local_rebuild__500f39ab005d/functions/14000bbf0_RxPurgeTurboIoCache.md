# RxPurgeTurboIoCache

- ea: `0x14000bbf0`
- end: `0x14000be51`
- name: `RxPurgeTurboIoCache`
- size: `609`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140008e50`
- `0x140057660`

## callees

- `0x1400037e0`
- `0x14000bbf0`
- `0x140014d10`
- `0x140015230`
- `0x140025d00`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000bdf6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bdf6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027643`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140027643`

## pseudocode

```c
__int64 __fastcall RxPurgeTurboIoCache(__int64 a1, char a2)
{
  __int64 v2; // rax
  __int64 v5; // rbx
  __int64 result; // rax
  __int64 v7; // rcx
  struct _RX_CONTEXT *v8; // rsi
  _QWORD *v9; // rcx
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rdx
  _QWORD *v14; // rdx
  _QWORD **v15; // rcx
  __int64 i; // rbp
  __int64 v17; // rsi
  KIRQL v18; // r8
  _QWORD **v19; // rdx
  _OWORD v20[3]; // [rsp+30h] [rbp-38h] BYREF

  v2 = *(_QWORD *)(a1 + 304);
  v20[0] = 0;
  v5 = *(_QWORD *)(v2 + 328);
  *((_QWORD *)&v20[0] + 1) = v20;
  *(_QWORD *)&v20[0] = v20;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      18,
      (unsigned int)WPP_d414fc76462934e262300deaf9706329_Traceguids,
      a1,
      a1 + 360);
  }
  if ( v5 )
  {
    if ( a2 )
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 28));
    for ( i = 0; (unsigned int)i < (unsigned __int16)RxMaxNumaNodes; i = (unsigned int)(i + 1) )
    {
      v17 = *(_QWORD *)(v5 + 8 * i + 32);
      v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v17);
      v19 = (_QWORD **)(v17 + 16);
      while ( 1 )
      {
        v9 = *v19;
        if ( *v19 == v19 )
          break;
        if ( (_QWORD **)v9[1] != v19 )
          goto LABEL_10;
        v10 = (_QWORD *)*v9;
        if ( *(_QWORD **)(*v9 + 8LL) != v9 )
          goto LABEL_10;
        *v19 = v10;
        v10[1] = v19;
        *((_DWORD *)v9 - 62) &= ~0x80000u;
        _InterlockedOr((volatile signed __int32 *)v9 - 60, 2u);
        _InterlockedIncrement((volatile signed __int32 *)v9 - 91);
        v11 = (_QWORD *)*((_QWORD *)&v20[0] + 1);
        if ( **((_OWORD ***)&v20[0] + 1) != v20 )
          goto LABEL_10;
        v9[1] = *((_QWORD *)&v20[0] + 1);
        *v9 = v20;
        *v11 = v9;
        *((_QWORD *)&v20[0] + 1) = v9;
      }
      v15 = (_QWORD **)(v17 + 32);
      while ( 1 )
      {
        v12 = *v15;
        if ( *v15 == v15 )
          break;
        if ( (_QWORD **)v12[1] != v15 )
          goto LABEL_10;
        v13 = (_QWORD *)*v12;
        if ( *(_QWORD **)(*v12 + 8LL) != v12 )
          goto LABEL_10;
        *v15 = v13;
        v13[1] = v15;
        *((_DWORD *)v12 - 62) &= ~0x80000u;
        _InterlockedOr((volatile signed __int32 *)v12 - 60, 2u);
        _InterlockedIncrement((volatile signed __int32 *)v12 - 91);
        v14 = (_QWORD *)*((_QWORD *)&v20[0] + 1);
        if ( **((_OWORD ***)&v20[0] + 1) != v20 )
          goto LABEL_10;
        v12[1] = *((_QWORD *)&v20[0] + 1);
        *v12 = v20;
        *v14 = v12;
        *((_QWORD *)&v20[0] + 1) = v12;
      }
      *(_DWORD *)(v17 + 8) = 0;
      KeReleaseSpinLock((PKSPIN_LOCK)v17, v18);
    }
  }
  while ( 1 )
  {
    result = *(_QWORD *)&v20[0];
    if ( *(_OWORD **)&v20[0] == v20 )
      break;
    if ( *(_OWORD **)(*(_QWORD *)&v20[0] + 8LL) != v20
      || (v7 = **(_QWORD **)&v20[0], *(_QWORD *)(**(_QWORD **)&v20[0] + 8LL) != *(_QWORD *)&v20[0]) )
    {
LABEL_10:
      __fastfail(3u);
    }
    *(_QWORD *)&v20[0] = **(_QWORD **)&v20[0];
    *(_QWORD *)(v7 + 8) = v20;
    v8 = (struct _RX_CONTEXT *)(result - 368);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_d414fc76462934e262300deaf9706329_Traceguids,
        result - 368,
        a1);
    }
    (**(void (__fastcall ***)(struct _RX_CONTEXT *, _QWORD))(v5 + 16))(v8, 0);
    RxDereferenceAndDeleteRxContext_Real(v8);
  }
  return result;
}

```

## disassembly

```asm
0x14000bbf0  push    rbx
0x14000bbf2  push    rsi
0x14000bbf3  push    rdi
0x14000bbf4  push    r14
0x14000bbf6  sub     rsp, 48h
0x14000bbfa  mov     rax, [rcx+130h]
0x14000bc01  xorps   xmm0, xmm0
0x14000bc04  movups  [rsp+68h+var_38], xmm0
0x14000bc09  movzx   esi, dl
0x14000bc0c  mov     rdi, rcx
0x14000bc0f  mov     rbx, [rax+148h]
0x14000bc16  lea     rax, [rsp+68h+var_38]
0x14000bc1b  mov     qword ptr [rsp+68h+var_38+8], rax
0x14000bc20  lea     rax, [rsp+68h+var_38]
0x14000bc25  mov     qword ptr [rsp+68h+var_38], rax
0x14000bc2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc31  lea     r14, WPP_GLOBAL_Control
0x14000bc38  cmp     rcx, r14
0x14000bc3b  jz      short loc_14000BC4A
0x14000bc3d  test    dword ptr [rcx+2Ch], 4000h
0x14000bc44  jnz     loc_14000BD9A
0x14000bc4a  mov     [rsp+68h+arg_0], rbp
0x14000bc4f  test    rbx, rbx
0x14000bc52  jnz     loc_14000BDCD
0x14000bc58  mov     rax, qword ptr [rsp+68h+var_38]
0x14000bc5d  lea     rcx, [rsp+68h+var_38]
0x14000bc62  cmp     rax, rcx
0x14000bc65  jz      short loc_14000BCBB
0x14000bc67  lea     rcx, [rsp+68h+var_38]
0x14000bc6c  cmp     [rax+8], rcx
0x14000bc70  jnz     short loc_14000BCCB
0x14000bc72  mov     rcx, [rax]
0x14000bc75  cmp     [rcx+8], rax
0x14000bc79  jnz     short loc_14000BCCB
0x14000bc7b  lea     rdx, [rsp+68h+var_38]
0x14000bc80  mov     qword ptr [rsp+68h+var_38], rcx
0x14000bc85  mov     [rcx+8], rdx
0x14000bc89  lea     rsi, [rax-170h]
0x14000bc90  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc97  cmp     rcx, r14
0x14000bc9a  jnz     loc_14000BE18
0x14000bca0  mov     rax, [rbx+10h]
0x14000bca4  xor     edx, edx
0x14000bca6  mov     rcx, rsi
0x14000bca9  mov     rax, [rax]
0x14000bcac  call    _guard_dispatch_icall
0x14000bcb1  mov     rcx, rsi; RxContext
0x14000bcb4  call    RxDereferenceAndDeleteRxContext_Real
0x14000bcb9  jmp     short loc_14000BC58
0x14000bcbb  mov     rbp, [rsp+68h+arg_0]
0x14000bcc0  add     rsp, 48h
0x14000bcc4  pop     r14
0x14000bcc6  pop     rdi
0x14000bcc7  pop     rsi
0x14000bcc8  pop     rbx
0x14000bcc9  retn
0x14000bccb  mov     ecx, 3
0x14000bcd0  int     29h; Win8: RtlFailFast(ecx)
0x14000bcd2  mov     rcx, [rdx]
0x14000bcd5  cmp     rcx, rdx
0x14000bcd8  jz      loc_14000BDDF
0x14000bcde  cmp     [rcx+8], rdx
0x14000bce2  jnz     short loc_14000BCCB
0x14000bce4  mov     rax, [rcx]
0x14000bce7  cmp     [rax+8], rcx
0x14000bceb  jnz     short loc_14000BCCB
0x14000bced  mov     [rdx], rax
0x14000bcf0  mov     [rax+8], rdx
0x14000bcf4  and     dword ptr [rcx-0F8h], 0FFF7FFFFh
0x14000bcfe  lock or dword ptr [rcx-0F0h], 2
0x14000bd06  lock inc dword ptr [rcx-16Ch]
0x14000bd0d  mov     rax, qword ptr [rsp+68h+var_38+8]
0x14000bd12  lea     r9, [rsp+68h+var_38]
0x14000bd17  cmp     [rax], r9
0x14000bd1a  jnz     short loc_14000BCCB
0x14000bd1c  mov     [rcx+8], rax
0x14000bd20  lea     r9, [rsp+68h+var_38]
0x14000bd25  mov     [rcx], r9
0x14000bd28  mov     [rax], rcx
0x14000bd2b  mov     qword ptr [rsp+68h+var_38+8], rcx
0x14000bd30  jmp     short loc_14000BCD2
0x14000bd32  mov     rax, [rcx]
0x14000bd35  cmp     rax, rcx
0x14000bd38  jz      loc_14000BDE8
0x14000bd3e  cmp     [rax+8], rcx
0x14000bd42  jnz     short loc_14000BCCB
0x14000bd44  mov     rdx, [rax]
0x14000bd47  cmp     [rdx+8], rax
0x14000bd4b  jnz     loc_14000BCCB
0x14000bd51  mov     [rcx], rdx
0x14000bd54  mov     [rdx+8], rcx
0x14000bd58  and     dword ptr [rax-0F8h], 0FFF7FFFFh
0x14000bd62  lock or dword ptr [rax-0F0h], 2
0x14000bd6a  lock inc dword ptr [rax-16Ch]
0x14000bd71  mov     rdx, qword ptr [rsp+68h+var_38+8]
0x14000bd76  lea     r9, [rsp+68h+var_38]
0x14000bd7b  cmp     [rdx], r9
0x14000bd7e  jnz     loc_14000BCCB
0x14000bd84  mov     [rax+8], rdx
0x14000bd88  lea     r9, [rsp+68h+var_38]
0x14000bd8d  mov     [rax], r9
0x14000bd90  mov     [rdx], rax
0x14000bd93  mov     qword ptr [rsp+68h+var_38+8], rax
0x14000bd98  jmp     short loc_14000BD32
0x14000bd9a  cmp     byte ptr [rcx+29h], 2
0x14000bd9e  jb      loc_14000BC4A
0x14000bda4  mov     rcx, [rcx+18h]
0x14000bda8  lea     rax, [rdi+168h]
0x14000bdaf  mov     edx, 12h
0x14000bdb4  mov     [rsp+68h+var_48], rax
0x14000bdb9  mov     r9, rdi
0x14000bdbc  lea     r8, WPP_d414fc76462934e262300deaf9706329_Traceguids
0x14000bdc3  call    WPP_SF_qZ
0x14000bdc8  jmp     loc_14000BC4A
0x14000bdcd  test    sil, sil
0x14000bdd0  jz      loc_14002762A
0x14000bdd6  lock inc dword ptr [rbx+1Ch]
0x14000bdda  jmp     loc_14002762A
0x14000bddf  lea     rcx, [rsi+20h]
0x14000bde3  jmp     loc_14000BD32
0x14000bde8  movzx   edx, r8b; NewIrql
0x14000bdec  mov     dword ptr [rsi+8], 0
0x14000bdf3  mov     rcx, rsi; SpinLock
0x14000bdf6  call    cs:__imp_KeReleaseSpinLock
0x14000bdfd  nop     dword ptr [rax+rax+00h]
0x14000be02  movzx   eax, cs:RxMaxNumaNodes
0x14000be09  inc     ebp
0x14000be0b  cmp     ebp, eax
0x14000be0d  jb      loc_14002763B
0x14000be13  jmp     loc_14000BC58
0x14000be18  test    dword ptr [rcx+2Ch], 4000h
0x14000be1f  jz      loc_14000BCA0
0x14000be25  cmp     byte ptr [rcx+29h], 4
0x14000be29  jb      loc_14000BCA0
0x14000be2f  mov     rcx, [rcx+18h]
0x14000be33  lea     r8, WPP_d414fc76462934e262300deaf9706329_Traceguids
0x14000be3a  mov     edx, 13h
0x14000be3f  mov     [rsp+68h+var_48], rdi
0x14000be44  mov     r9, rsi
0x14000be47  call    WPP_SF_qq
0x14000be4c  jmp     loc_14000BCA0
0x14002762a  xor     ebp, ebp
0x14002762c  xor     eax, eax
0x14002762e  cmp     ax, cs:RxMaxNumaNodes
0x140027635  jnb     loc_14000BC58
0x14002763b  mov     rsi, [rbx+rbp*8+20h]
0x140027640  mov     rcx, rsi; SpinLock
0x140027643  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002764a  nop     dword ptr [rax+rax+00h]
0x14002764f  movzx   r8d, al
0x140027653  lea     rdx, [rsi+10h]
0x140027657  jmp     loc_14000BCD2
```
