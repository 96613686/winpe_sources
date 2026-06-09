# NatpCleanupRedirect

- ea: `0x140019cec`
- end: `0x14001a0e7`
- name: `NatpCleanupRedirect`
- size: `1019`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140017168`
- `0x140017718`
- `0x14001a0f0`
- `0x14001a4c0`
- `0x14001a5e0`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x140011624`
- `0x140019cec`
- `0x14001bde0`
- `0x14002c710`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140019f8e`
- `ntoskrnl!ObfDereferenceObject` at `0x140019f8e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140019dee`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001a09b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140019dee`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001a09b`
- `ntoskrnl!IofCompleteRequest` at `0x14001a044`
- `ntoskrnl!IofCompleteRequest` at `0x14001a044`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019ed8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019f13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019f6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a05a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019ed8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019f13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019f6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a05a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140019e22`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001a06d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140019e22`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001a06d`

## pseudocode

```c
void __fastcall NatpCleanupRedirect(char *P, unsigned int a2)
{
  int v4; // eax
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rax
  char **v8; // rcx
  char *v9; // rdi
  __int64 v10; // rdx
  char **v11; // rax
  __int64 v12; // rax
  char **v13; // rcx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rdx
  _QWORD *v17; // rdi
  __int64 v18; // rcx
  _QWORD *v19; // rax
  _QWORD *v20; // rdi
  _QWORD *v21; // rdi
  __int64 v22; // rcx
  _QWORD *v23; // rax
  void *v24; // rcx
  __int64 v25; // rdi
  __int64 v26; // rax
  _QWORD *v27; // rax
  __int64 v28; // rdx
  _QWORD *v29; // rcx
  _QWORD *v30; // rax
  _OWORD *v31; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 90, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids, a2);
  }
  v4 = *((_DWORD *)P + 28);
  if ( (v4 & 0x20000000) != 0 )
  {
    *((_DWORD *)P + 60) = a2;
    *((_DWORD *)P + 28) = v4 | 0x10000000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      v6 = 91;
LABEL_54:
      WPP_SF_(v5->AttachedDevice, v6, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids);
      return;
    }
    return;
  }
  if ( (v4 & 0x8000000) == 0 )
  {
    if ( *(char **)P != P )
      _InterlockedDecrement(&RedirectCount);
    v7 = *(_QWORD *)P;
    if ( *(char **)(*(_QWORD *)P + 8LL) == P )
    {
      v8 = (char **)*((_QWORD *)P + 1);
      if ( *v8 == P )
      {
        *v8 = (char *)v7;
        v9 = P + 16;
        *(_QWORD *)(v7 + 8) = v8;
        if ( (*((_DWORD *)P + 28) & 0x40000000) != 0 )
        {
          KeAcquireSpinLockAtDpcLevel(&RedirectCompletionLock);
          v10 = *(_QWORD *)v9;
          if ( *(char **)(*(_QWORD *)v9 + 8LL) != v9 )
            goto LABEL_56;
          v11 = (char **)*((_QWORD *)P + 3);
          if ( *v11 != v9 )
            goto LABEL_56;
          *v11 = (char *)v10;
          *(_QWORD *)(v10 + 8) = v11;
          KeReleaseSpinLockFromDpcLevel(&RedirectCompletionLock);
        }
        else
        {
          v12 = *(_QWORD *)v9;
          if ( *(char **)(*(_QWORD *)v9 + 8LL) != v9 )
            goto LABEL_56;
          v13 = (char **)*((_QWORD *)P + 3);
          if ( *v13 != v9 )
            goto LABEL_56;
          *v13 = (char *)v12;
          *(_QWORD *)(v12 + 8) = v13;
        }
        v14 = P + 32;
        v15 = *((_QWORD *)P + 4);
        if ( *(char **)(v15 + 8) == P + 32 )
        {
          v16 = (_QWORD *)*((_QWORD *)P + 5);
          if ( (_QWORD *)*v16 == v14 )
          {
            *v16 = v15;
            *(_QWORD *)(v15 + 8) = v16;
            *((_QWORD *)P + 3) = P + 16;
            *(_QWORD *)v9 = v9;
            v17 = (_QWORD *)*((_QWORD *)P + 10);
            *((_QWORD *)P + 1) = P;
            *(_QWORD *)P = P;
            *((_QWORD *)P + 5) = P + 32;
            *v14 = v14;
            *((_QWORD *)P + 10) = 0;
            if ( v17 && (_QWORD *)v17[2] == v17 + 2 )
            {
              removeRhizome(*((_QWORD *)P + 13), v17[4]);
              v18 = *v17;
              if ( *(_QWORD **)(*v17 + 8LL) != v17 )
                goto LABEL_56;
              v19 = (_QWORD *)v17[1];
              if ( (_QWORD *)*v19 != v17 )
                goto LABEL_56;
              *v19 = v18;
              *(_QWORD *)(v18 + 8) = v19;
              ExFreePoolWithTag(v17, 0);
            }
            v20 = (_QWORD *)*((_QWORD *)P + 11);
            *((_QWORD *)P + 11) = 0;
            if ( v20 && (_QWORD *)v20[2] == v20 + 2 )
            {
              removeRhizome(qword_140031F90, v20[4]);
              ExFreePoolWithTag(v20, 0);
            }
            v21 = (_QWORD *)*((_QWORD *)P + 12);
            *((_QWORD *)P + 12) = 0;
            if ( v21 && (_QWORD *)v21[2] == v21 + 2 )
            {
              removeRhizome(RedirectRhizome, v21[4]);
              v22 = *v21;
              if ( *(_QWORD **)(*v21 + 8LL) != v21 )
                goto LABEL_56;
              v23 = (_QWORD *)v21[1];
              if ( (_QWORD *)*v23 != v21 )
                goto LABEL_56;
              *v23 = v22;
              *(_QWORD *)(v22 + 8) = v23;
              ExFreePoolWithTag(v21, 0);
            }
            v24 = (void *)*((_QWORD *)P + 18);
            v25 = *((_QWORD *)P + 19);
            if ( v24 )
              ObfDereferenceObject(v24);
            v26 = *((_QWORD *)P + 16);
            if ( !v26 )
            {
LABEL_48:
              ExFreePoolWithTag(P, 0);
              KeReleaseSpinLockFromDpcLevel(&RedirectLock);
              if ( v25 )
                ((void (__fastcall *)(__int64, __int64))qword_140032070)(qword_140032058, v25);
              KeAcquireSpinLockAtDpcLevel(&RedirectLock);
              v5 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
              {
                v6 = 93;
                goto LABEL_54;
              }
              return;
            }
            v27 = (_QWORD *)(v26 + 168);
            v28 = *v27;
            if ( *(_QWORD **)(*v27 + 8LL) == v27 )
            {
              v29 = (_QWORD *)v27[1];
              if ( (_QWORD *)*v29 == v27 )
              {
                *v29 = v28;
                *(_QWORD *)(v28 + 8) = v29;
                v30 = (_QWORD *)(*((_QWORD *)P + 16) + 168LL);
                v30[1] = v30;
                *v30 = v30;
                if ( _InterlockedExchange64((volatile __int64 *)(*((_QWORD *)P + 16) + 104LL), 0) )
                {
                  v31 = *(_OWORD **)(*((_QWORD *)P + 16) + 24LL);
                  *v31 = *((_OWORD *)P + 10);
                  v31[1] = *((_OWORD *)P + 11);
                  v31[2] = *((_OWORD *)P + 12);
                  *(_DWORD *)(*((_QWORD *)P + 16) + 48LL) = a2;
                  *(_QWORD *)(*((_QWORD *)P + 16) + 56LL) = 48;
                  IofCompleteRequest(*((PIRP *)P + 16), 0);
                  ReleaseComponentReference();
                }
                goto LABEL_48;
              }
            }
          }
        }
      }
    }
LABEL_56:
    __fastfail(3u);
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    v6 = 92;
    goto LABEL_54;
  }
}

```

## disassembly

```asm
0x140019cec  push    rbx
0x140019cee  push    rsi
0x140019cef  push    rdi
0x140019cf0  push    r13
0x140019cf2  sub     rsp, 28h
0x140019cf6  mov     esi, edx
0x140019cf8  mov     rbx, rcx
0x140019cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140019d02  lea     r13, WPP_GLOBAL_Control
0x140019d09  cmp     rcx, r13
0x140019d0c  jz      short loc_140019D33
0x140019d0e  mov     eax, [rcx+2Ch]
0x140019d11  test    al, 1
0x140019d13  jz      short loc_140019D33
0x140019d15  cmp     byte ptr [rcx+29h], 6
0x140019d19  jb      short loc_140019D33
0x140019d1b  mov     rcx, [rcx+18h]
0x140019d1f  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x140019d26  mov     edx, 5Ah ; 'Z'
0x140019d2b  mov     r9d, esi
0x140019d2e  call    WPP_SF_d
0x140019d33  mov     eax, [rbx+70h]
0x140019d36  bt      eax, 1Dh
0x140019d3a  jnb     short loc_140019D78
0x140019d3c  bts     eax, 1Ch
0x140019d40  mov     [rbx+0F0h], esi
0x140019d46  mov     [rbx+70h], eax
0x140019d49  mov     rcx, cs:WPP_GLOBAL_Control
0x140019d50  cmp     rcx, r13
0x140019d53  jz      loc_14001A0D5
0x140019d59  mov     eax, [rcx+2Ch]
0x140019d5c  test    al, 1
0x140019d5e  jz      loc_14001A0D5
0x140019d64  cmp     byte ptr [rcx+29h], 6
0x140019d68  jb      loc_14001A0D5
0x140019d6e  mov     edx, 5Bh ; '['
0x140019d73  jmp     loc_14001A0C5
0x140019d78  bt      eax, 1Bh
0x140019d7c  jnb     short loc_140019DAD
0x140019d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140019d85  cmp     rcx, r13
0x140019d88  jz      loc_14001A0D5
0x140019d8e  mov     eax, [rcx+2Ch]
0x140019d91  test    al, 1
0x140019d93  jz      loc_14001A0D5
0x140019d99  cmp     byte ptr [rcx+29h], 6
0x140019d9d  jb      loc_14001A0D5
0x140019da3  mov     edx, 5Ch ; '\'
0x140019da8  jmp     loc_14001A0C5
0x140019dad  cmp     [rbx], rbx
0x140019db0  jz      short loc_140019DB9
0x140019db2  lock dec cs:RedirectCount
0x140019db9  mov     rax, [rbx]
0x140019dbc  cmp     [rax+8], rbx
0x140019dc0  jnz     loc_14001A0E0
0x140019dc6  mov     rcx, [rbx+8]
0x140019dca  cmp     [rcx], rbx
0x140019dcd  jnz     loc_14001A0E0
0x140019dd3  mov     [rcx], rax
0x140019dd6  lea     rdi, [rbx+10h]
0x140019dda  mov     [rax+8], rcx
0x140019dde  test    dword ptr [rbx+70h], 40000000h
0x140019de5  jz      short loc_140019E30
0x140019de7  lea     rcx, RedirectCompletionLock; SpinLock
0x140019dee  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140019df5  nop     dword ptr [rax+rax+00h]
0x140019dfa  mov     rdx, [rdi]
0x140019dfd  cmp     [rdx+8], rdi
0x140019e01  jnz     loc_14001A0E0
0x140019e07  mov     rax, [rdi+8]
0x140019e0b  cmp     [rax], rdi
0x140019e0e  jnz     loc_14001A0E0
0x140019e14  mov     [rax], rdx
0x140019e17  lea     rcx, RedirectCompletionLock; SpinLock
0x140019e1e  mov     [rdx+8], rax
0x140019e22  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140019e29  nop     dword ptr [rax+rax+00h]
0x140019e2e  jmp     short loc_140019E51
0x140019e30  mov     rax, [rdi]
0x140019e33  cmp     [rax+8], rdi
0x140019e37  jnz     loc_14001A0E0
0x140019e3d  mov     rcx, [rdi+8]
0x140019e41  cmp     [rcx], rdi
0x140019e44  jnz     loc_14001A0E0
0x140019e4a  mov     [rcx], rax
0x140019e4d  mov     [rax+8], rcx
0x140019e51  lea     rax, [rbx+20h]
0x140019e55  mov     rcx, [rax]
0x140019e58  cmp     [rcx+8], rax
0x140019e5c  jnz     loc_14001A0E0
0x140019e62  mov     rdx, [rax+8]
0x140019e66  cmp     [rdx], rax
0x140019e69  jnz     loc_14001A0E0
0x140019e6f  mov     [rdx], rcx
0x140019e72  mov     [rcx+8], rdx
0x140019e76  mov     [rdi+8], rdi
0x140019e7a  mov     [rdi], rdi
0x140019e7d  mov     rdi, [rbx+50h]
0x140019e81  mov     [rbx+8], rbx
0x140019e85  mov     [rbx], rbx
0x140019e88  mov     [rax+8], rax
0x140019e8c  mov     [rax], rax
0x140019e8f  mov     qword ptr [rbx+50h], 0
0x140019e97  test    rdi, rdi
0x140019e9a  jz      short loc_140019EE4
0x140019e9c  lea     rax, [rdi+10h]
0x140019ea0  cmp     [rax], rax
0x140019ea3  jnz     short loc_140019EE4
0x140019ea5  mov     rdx, [rdi+20h]
0x140019ea9  mov     rcx, [rbx+68h]
0x140019ead  call    removeRhizome
0x140019eb2  mov     rcx, [rdi]
0x140019eb5  cmp     [rcx+8], rdi
0x140019eb9  jnz     loc_14001A0E0
0x140019ebf  mov     rax, [rdi+8]
0x140019ec3  cmp     [rax], rdi
0x140019ec6  jnz     loc_14001A0E0
0x140019ecc  mov     [rax], rcx
0x140019ecf  xor     edx, edx; Tag
0x140019ed1  mov     [rcx+8], rax
0x140019ed5  mov     rcx, rdi; P
0x140019ed8  call    cs:__imp_ExFreePoolWithTag
0x140019edf  nop     dword ptr [rax+rax+00h]
0x140019ee4  mov     rdi, [rbx+58h]
0x140019ee8  mov     qword ptr [rbx+58h], 0
0x140019ef0  test    rdi, rdi
0x140019ef3  jz      short loc_140019F1F
0x140019ef5  lea     rax, [rdi+10h]
0x140019ef9  cmp     [rax], rax
0x140019efc  jnz     short loc_140019F1F
0x140019efe  mov     rdx, [rdi+20h]
0x140019f02  lea     rcx, qword_140031F90
0x140019f09  call    removeRhizome
0x140019f0e  xor     edx, edx; Tag
0x140019f10  mov     rcx, rdi; P
0x140019f13  call    cs:__imp_ExFreePoolWithTag
0x140019f1a  nop     dword ptr [rax+rax+00h]
0x140019f1f  mov     rdi, [rbx+60h]
0x140019f23  mov     qword ptr [rbx+60h], 0
0x140019f2b  test    rdi, rdi
0x140019f2e  jz      short loc_140019F7B
0x140019f30  lea     rax, [rdi+10h]
0x140019f34  cmp     [rax], rax
0x140019f37  jnz     short loc_140019F7B
0x140019f39  mov     rdx, [rdi+20h]
0x140019f3d  lea     rcx, RedirectRhizome
0x140019f44  call    removeRhizome
0x140019f49  mov     rcx, [rdi]
0x140019f4c  cmp     [rcx+8], rdi
0x140019f50  jnz     loc_14001A0E0
0x140019f56  mov     rax, [rdi+8]
0x140019f5a  cmp     [rax], rdi
0x140019f5d  jnz     loc_14001A0E0
0x140019f63  mov     [rax], rcx
0x140019f66  xor     edx, edx; Tag
0x140019f68  mov     [rcx+8], rax
0x140019f6c  mov     rcx, rdi; P
0x140019f6f  call    cs:__imp_ExFreePoolWithTag
0x140019f76  nop     dword ptr [rax+rax+00h]
0x140019f7b  mov     rcx, [rbx+90h]; Object
0x140019f82  mov     rdi, [rbx+98h]
0x140019f89  test    rcx, rcx
0x140019f8c  jz      short loc_140019F9A
0x140019f8e  call    cs:__imp_ObfDereferenceObject
0x140019f95  nop     dword ptr [rax+rax+00h]
0x140019f9a  mov     rax, [rbx+80h]
0x140019fa1  test    rax, rax
0x140019fa4  jz      loc_14001A055
0x140019faa  add     rax, 0A8h
0x140019fb0  mov     rdx, [rax]
0x140019fb3  cmp     [rdx+8], rax
0x140019fb7  jnz     loc_14001A0E0
0x140019fbd  mov     rcx, [rax+8]
0x140019fc1  cmp     [rcx], rax
0x140019fc4  jnz     loc_14001A0E0
0x140019fca  mov     [rcx], rdx
0x140019fcd  mov     [rdx+8], rcx
0x140019fd1  xor     ecx, ecx
0x140019fd3  mov     rax, [rbx+80h]
0x140019fda  add     rax, 0A8h
0x140019fe0  mov     [rax+8], rax
0x140019fe4  mov     [rax], rax
0x140019fe7  mov     rax, [rbx+80h]
0x140019fee  xchg    rcx, [rax+68h]
0x140019ff2  test    rcx, rcx
0x140019ff5  jz      short loc_14001A055
0x140019ff7  mov     rax, [rbx+80h]
0x140019ffe  xor     edx, edx; PriorityBoost
0x14001a000  movups  xmm0, xmmword ptr [rbx+0A0h]
0x14001a007  mov     rcx, [rax+18h]
0x14001a00b  movups  xmmword ptr [rcx], xmm0
0x14001a00e  movups  xmm1, xmmword ptr [rbx+0B0h]
0x14001a015  movups  xmmword ptr [rcx+10h], xmm1
0x14001a019  movups  xmm0, xmmword ptr [rbx+0C0h]
0x14001a020  movups  xmmword ptr [rcx+20h], xmm0
0x14001a024  mov     rax, [rbx+80h]
0x14001a02b  mov     [rax+30h], esi
0x14001a02e  mov     rax, [rbx+80h]
0x14001a035  mov     qword ptr [rax+38h], 30h ; '0'
0x14001a03d  mov     rcx, [rbx+80h]; Irp
0x14001a044  call    cs:__imp_IofCompleteRequest
0x14001a04b  nop     dword ptr [rax+rax+00h]
0x14001a050  call    ReleaseComponentReference
0x14001a055  xor     edx, edx; Tag
0x14001a057  mov     rcx, rbx; P
0x14001a05a  call    cs:__imp_ExFreePoolWithTag
0x14001a061  nop     dword ptr [rax+rax+00h]
0x14001a066  lea     rcx, RedirectLock; SpinLock
0x14001a06d  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001a074  nop     dword ptr [rax+rax+00h]
0x14001a079  test    rdi, rdi
0x14001a07c  jz      short loc_14001A094
0x14001a07e  mov     rax, cs:qword_140032070
0x14001a085  mov     rdx, rdi
0x14001a088  mov     rcx, cs:qword_140032058
0x14001a08f  call    _guard_dispatch_icall
0x14001a094  lea     rcx, RedirectLock; SpinLock
0x14001a09b  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001a0a2  nop     dword ptr [rax+rax+00h]
0x14001a0a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a0ae  cmp     rcx, r13
0x14001a0b1  jz      short loc_14001A0D5
0x14001a0b3  mov     eax, [rcx+2Ch]
0x14001a0b6  test    al, 1
0x14001a0b8  jz      short loc_14001A0D5
0x14001a0ba  cmp     byte ptr [rcx+29h], 6
0x14001a0be  jb      short loc_14001A0D5
0x14001a0c0  mov     edx, 5Dh ; ']'
0x14001a0c5  mov     rcx, [rcx+18h]
0x14001a0c9  lea     r8, WPP_f370ec4bbdd23e8f2eb01f331622eaa7_Traceguids
0x14001a0d0  call    WPP_SF_
0x14001a0d5  add     rsp, 28h
0x14001a0d9  pop     r13
0x14001a0db  pop     rdi
0x14001a0dc  pop     rsi
0x14001a0dd  pop     rbx
0x14001a0de  retn
0x14001a0e0  mov     ecx, 3
0x14001a0e5  int     29h; Win8: RtlFailFast(ecx)
```
