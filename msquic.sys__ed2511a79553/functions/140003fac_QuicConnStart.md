# QuicConnStart

- ea: `0x140003fac`
- end: `0x14000445a`
- name: `QuicConnStart`
- size: `1198`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c774`

## callees

- `0x140001860`
- `0x140003b8c`
- `0x140003fac`
- `0x140004460`
- `0x140004878`
- `0x140004e2c`
- `0x14000524c`
- `0x140005aa4`
- `0x140008568`
- `0x14001c5b8`
- `0x14001c638`
- `0x1400206e8`
- `0x1400337e4`
- `0x140039e18`
- `0x14003c8e0`
- `0x14003ce00`
- `0x14003ec10`
- `0x14003fdf8`
- `0x14003fea4`
- `0x1400427e0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003ff8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003ff8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004024`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004024`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004058`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004154`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004058`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004154`
- `ntoskrnl!ExAllocatePool2` at `0x140004338`
- `ntoskrnl!ExAllocatePool2` at `0x140004338`
- `NDIS!NdisSetThreadObjectCompartmentId` at `0x14000410e`
- `NDIS!NdisSetThreadObjectCompartmentId` at `0x1400041b0`
- `NDIS!NdisSetThreadObjectCompartmentId` at `0x14000410e`
- `NDIS!NdisSetThreadObjectCompartmentId` at `0x1400041b0`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400040e7`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x1400040e7`

## string_xrefs

- `0x140004129`: `Set current compartment Id`
- `0x14000409b`: `Path->Binding == ((void *)0)`

## pseudocode

```c
__int64 __fastcall QuicConnStart(__int64 a1, __int64 a2, __int16 a3, void *a4, __int16 a5, char a6)
{
  __int64 v8; // r12
  __int64 v10; // rdx
  __int64 v11; // r14
  int v12; // r15d
  char v13; // bl
  char v15; // r14
  int v16; // ecx
  int Binding; // ebx
  __int64 v18; // rcx
  int v19; // r9d
  bool v20; // zf
  int v21; // eax
  bool v22; // sf
  char v23; // cl
  __int64 v24; // r9
  int v25; // ecx
  __int64 v26; // rbx
  __int64 Pool2; // rax
  int v28; // r9d
  __int64 v29; // rax
  _QWORD v31[10]; // [rsp+40h] [rbp-49h] BYREF

  v8 = a2;
  if ( (*(_BYTE *)(a1 + 248) & 0x14) == 0 )
  {
    *(_BYTE *)(*(_QWORD *)(a1 + 80) + 88LL) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)(a1 + 80) + 80LL));
    v10 = *(_QWORD *)(a1 + 80);
    v11 = *(_QWORD *)(v10 + 136);
    v12 = *(_DWORD *)(v10 + 24);
    v13 = *(_BYTE *)(v10 + 16);
    KeReleaseSpinLock((PKSPIN_LOCK)(v10 + 80), *(_BYTE *)(v10 + 88));
    if ( (v13 & 4) != 0 )
    {
      QuicConnShutdown(a1, v12, v11, 0, 0);
      goto LABEL_4;
    }
    if ( *(_QWORD *)(a1 + 360) )
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\connection.c", 1807, "Path->Binding == ((void *)0)");
    QuicConnApplyNewSettings(a1, 0, v8 + 96);
    if ( (*(_BYTE *)(a1 + 250) & 0x10) == 0 )
    {
      v15 = 0;
      *(_WORD *)(a1 + 376) = a3;
      if ( (unsigned int)NdisGetThreadObjectCompartmentId(KeGetCurrentThread()) != *(_DWORD *)(a2 + 56) )
      {
        Binding = NdisSetThreadObjectCompartmentId(KeGetCurrentThread());
        if ( Binding < 0 )
        {
          if ( (byte_14005C48B & 4) != 0 )
            McTemplateU0pqs_EtwWriteTransfer(
              v16,
              (unsigned int)QuicConnErrorStatus,
              a1,
              Binding,
              (__int64)"Set current compartment Id");
          goto LABEL_14;
        }
        v15 = 1;
      }
      Binding = CxPlatDataPathResolveAddress(qword_14005C590, a4, a1 + 376);
      if ( v15 )
        NdisSetThreadObjectCompartmentId(KeGetCurrentThread());
      if ( Binding < 0 )
        goto LABEL_14;
      *(_BYTE *)(a1 + 250) |= 0x10u;
      v8 = a2;
    }
    if ( (unsigned __int8)QuicAddrIsWildCard(a1 + 376) )
    {
      Binding = -1073741811;
      if ( (byte_14005C48B & 4) != 0 )
        McTemplateU0ps_EtwWriteTransfer(v18, QuicConnError, a1, "Invalid wildcard remote address in connection start");
    }
    else
    {
      *(_WORD *)(a1 + 378) = __ROR2__(a5, 8);
      if ( (byte_14005C489 & 0x40) != 0 )
      {
        LOBYTE(v19) = 28;
        McTemplateU0pubr1_EtwWriteTransfer(v18, (unsigned int)QuicConnRemoteAddrAdded, a1, v19, a1 + 376);
      }
      memset(v31, 0, 0x48u);
      if ( (*(_BYTE *)(a1 + 250) & 8) != 0 )
        v31[0] = a1 + 404;
      v20 = (*(_BYTE *)(a1 + 252) & 1) == 0;
      v31[1] = a1 + 376;
      if ( v20 )
        HIDWORD(v31[2]) = 0;
      else
        HIDWORD(v31[2]) = *(_DWORD *)(a1 + 428);
      LOWORD(v31[3]) = QuicPartitionIdGetIndex(*(unsigned __int16 *)(a1 + 270));
      v20 = (*(_BYTE *)(a1 + 251) & 2) == 0;
      LODWORD(v31[5]) = *(_DWORD *)(v8 + 56);
      v31[6] = *(_QWORD *)(v8 + 80);
      v21 = 0;
      if ( !v20 )
        v21 = 2;
      v22 = *(char *)(a1 + 236) < 0;
      LODWORD(v31[2]) = v21;
      if ( v22 )
      {
        v21 |= 8u;
        LODWORD(v31[2]) = v21;
      }
      v23 = *(_BYTE *)(a1 + 237);
      if ( (v23 & 1) != 0 )
      {
        v21 |= 0x10u;
        LODWORD(v31[2]) = v21;
      }
      if ( (v23 & 2) != 0 )
        LODWORD(v31[2]) = v21 | 0x20;
      Binding = QuicLibraryGetBinding(v31, a1 + 360);
      if ( Binding >= 0 )
      {
        if ( (*(_BYTE *)(a1 + 251) & 2) != 0 )
        {
          LOBYTE(v24) = *(_BYTE *)(a1 + 1312);
          v26 = QuicCidNewRandomSource(a1, 0, *(unsigned __int16 *)(a1 + 270), v24, a1 + 1314);
        }
        else
        {
          Pool2 = ExAllocatePool2(66, 56, 1144021841);
          v26 = Pool2;
          if ( Pool2 )
          {
            *(_QWORD *)(Pool2 + 32) = a1;
            *(_OWORD *)(Pool2 + 40) = 0;
          }
        }
        if ( v26 )
        {
          ++*(_QWORD *)(a1 + 304);
          if ( byte_14005C48A < 0 )
            McTemplateU0pxubr2_EtwWriteTransfer(
              v25,
              (unsigned int)QuicConnSourceCidAdded,
              a1,
              *(_QWORD *)(v26 + 48),
              *(_BYTE *)(v26 + 41),
              v26 + 56);
          *(_QWORD *)(v26 + 24) = *(_QWORD *)(a1 + 1280);
          *(_QWORD *)(a1 + 1280) = v26 + 24;
          if ( (unsigned __int8)QuicLookupAddLocalCid(*(_QWORD *)(a1 + 360) + 64LL, v26) )
          {
            *(_BYTE *)(a1 + 250) |= 8u;
            v29 = *(_QWORD *)(*(_QWORD *)(a1 + 360) + 32LL);
            *(_OWORD *)(a1 + 404) = *(_OWORD *)v29;
            *(_QWORD *)(a1 + 420) = *(_QWORD *)(v29 + 16);
            *(_DWORD *)(a1 + 428) = *(_DWORD *)(v29 + 24);
            if ( (byte_14005C489 & 0x40) != 0 )
            {
              LOBYTE(v28) = 28;
              McTemplateU0pubr1_EtwWriteTransfer(a1 + 404, (unsigned int)QuicConnLocalAddrAdded, a1, v28, a1 + 404);
            }
            *(_QWORD *)(a1 + 1608) = a4;
            Binding = QuicCryptoInitialize(a1 + 2784);
            if ( Binding < 0 )
              goto LABEL_17;
            Binding = QuicConnSetConfiguration(a1, v8);
LABEL_16:
            if ( Binding >= 0 )
              return (unsigned int)Binding;
LABEL_17:
            QuicConnCloseLocally(a1, 2 * (unsigned int)((a6 & 1) == 0) + 17, Binding);
            return (unsigned int)Binding;
          }
          QuicLibraryReleaseBinding(*(PVOID *)(a1 + 360));
          *(_QWORD *)(a1 + 360) = 0;
        }
        Binding = -1073741801;
      }
    }
LABEL_14:
    if ( a4 )
      ExFreePoolWithTag(a4, 0x32336351u);
    goto LABEL_16;
  }
LABEL_4:
  if ( a4 )
    ExFreePoolWithTag(a4, 0x32336351u);
  return 3221225860LL;
}

```

## disassembly

```asm
0x140003fac  mov     [rsp-8+arg_10], rbx
0x140003fb1  push    rbp
0x140003fb2  push    rsi
0x140003fb3  push    rdi
0x140003fb4  push    r12
0x140003fb6  push    r13
0x140003fb8  push    r14
0x140003fba  push    r15
0x140003fbc  lea     rbp, [rsp-17h]
0x140003fc1  sub     rsp, 0A0h
0x140003fc8  mov     rax, cs:__security_cookie
0x140003fcf  xor     rax, rsp
0x140003fd2  mov     [rbp+47h+var_40], rax
0x140003fd6  test    byte ptr [rcx+0F8h], 14h
0x140003fdd  mov     rsi, r9
0x140003fe0  movzx   r13d, r8w
0x140003fe4  mov     [rbp+47h+var_A0], rdx
0x140003fe8  mov     r12, rdx
0x140003feb  mov     rdi, rcx
0x140003fee  jnz     short loc_14000404B
0x140003ff0  mov     rcx, [rcx+50h]
0x140003ff4  add     rcx, 50h ; 'P'; SpinLock
0x140003ff8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003fff  nop     dword ptr [rax+rax+00h]
0x140004004  mov     rcx, [rdi+50h]
0x140004008  mov     [rcx+58h], al
0x14000400b  mov     rdx, [rdi+50h]
0x14000400f  mov     r14, [rdx+88h]
0x140004016  lea     rcx, [rdx+50h]; SpinLock
0x14000401a  mov     r15d, [rdx+18h]
0x14000401e  mov     bl, [rdx+10h]
0x140004021  mov     dl, [rdx+58h]; NewIrql
0x140004024  call    cs:__imp_KeReleaseSpinLock
0x14000402b  nop     dword ptr [rax+rax+00h]
0x140004030  test    bl, 4
0x140004033  jz      short loc_140004091
0x140004035  xor     r9d, r9d
0x140004038  mov     byte ptr [rsp+0D0h+var_B0], 0
0x14000403d  mov     r8, r14
0x140004040  mov     edx, r15d
0x140004043  mov     rcx, rdi
0x140004046  call    QuicConnShutdown
0x14000404b  test    rsi, rsi
0x14000404e  jz      short loc_140004064
0x140004050  mov     edx, 32336351h; Tag
0x140004055  mov     rcx, rsi; P
0x140004058  call    cs:__imp_ExFreePoolWithTag
0x14000405f  nop     dword ptr [rax+rax+00h]
0x140004064  mov     eax, 0C0000184h
0x140004069  mov     rcx, [rbp+47h+var_40]
0x14000406d  xor     rcx, rsp; StackCookie
0x140004070  call    __security_check_cookie
0x140004075  mov     rbx, [rsp+0D0h+arg_10]
0x14000407d  add     rsp, 0A0h
0x140004084  pop     r15
0x140004086  pop     r14
0x140004088  pop     r13
0x14000408a  pop     r12
0x14000408c  pop     rdi
0x14000408d  pop     rsi
0x14000408e  pop     rbp
0x14000408f  retn
0x140004091  cmp     qword ptr [rdi+168h], 0
0x140004099  jz      short loc_1400040B3
0x14000409b  lea     r8, aPathBindingVoi; "Path->Binding == ((void *)0)"
0x1400040a2  mov     edx, 70Fh
0x1400040a7  lea     rcx, aCW1SMsquicSrcC_0; "C:\\__w\\1\\s\\msquic\\src\\core\\conne"...
0x1400040ae  call    CxPlatLogAssert
0x1400040b3  lea     r8, [r12+60h]
0x1400040b8  xor     edx, edx
0x1400040ba  mov     rcx, rdi
0x1400040bd  call    QuicConnApplyNewSettings
0x1400040c2  test    byte ptr [rdi+0FAh], 10h
0x1400040c9  jnz     loc_1400041CB
0x1400040cf  lea     r12, [rdi+178h]
0x1400040d6  xor     r14b, r14b
0x1400040d9  mov     [r12], r13w
0x1400040de  mov     rcx, gs:188h
0x1400040e7  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x1400040ee  nop     dword ptr [rax+rax+00h]
0x1400040f3  mov     rdx, [rbp+47h+var_A0]
0x1400040f7  mov     r15d, eax
0x1400040fa  mov     edx, [rdx+38h]
0x1400040fd  cmp     eax, edx
0x1400040ff  jz      loc_14000418B
0x140004105  mov     rcx, gs:188h
0x14000410e  call    cs:__imp_NdisSetThreadObjectCompartmentId
0x140004115  nop     dword ptr [rax+rax+00h]
0x14000411a  mov     ebx, eax
0x14000411c  test    eax, eax
0x14000411e  jns     short loc_140004188
0x140004120  test    cs:byte_14005C48B, 4
0x140004127  jz      short loc_140004147
0x140004129  lea     rax, aSetCurrentComp; "Set current compartment Id"
0x140004130  mov     r9d, ebx
0x140004133  mov     r8, rdi
0x140004136  mov     [rsp+0D0h+var_B0], rax
0x14000413b  lea     rdx, QuicConnErrorStatus
0x140004142  call    McTemplateU0pqs_EtwWriteTransfer
0x140004147  test    rsi, rsi
0x14000414a  jz      short loc_140004160
0x14000414c  mov     edx, 32336351h; Tag
0x140004151  mov     rcx, rsi; P
0x140004154  call    cs:__imp_ExFreePoolWithTag
0x14000415b  nop     dword ptr [rax+rax+00h]
0x140004160  test    ebx, ebx
0x140004162  jns     short loc_140004181
0x140004164  mov     edx, [rbp+47h+arg_28]
0x140004167  xor     r9d, r9d
0x14000416a  not     edx
0x14000416c  movsxd  r8, ebx
0x14000416f  and     edx, 1
0x140004172  mov     rcx, rdi
0x140004175  lea     edx, ds:11h[rdx*2]
0x14000417c  call    QuicConnCloseLocally
0x140004181  mov     eax, ebx
0x140004183  jmp     loc_140004069
0x140004188  mov     r14b, 1
0x14000418b  mov     rcx, cs:qword_14005C590
0x140004192  mov     r8, r12
0x140004195  mov     rdx, rsi
0x140004198  call    CxPlatDataPathResolveAddress
0x14000419d  mov     ebx, eax
0x14000419f  test    r14b, r14b
0x1400041a2  jz      short loc_1400041BC
0x1400041a4  mov     rcx, gs:188h
0x1400041ad  mov     edx, r15d
0x1400041b0  call    cs:__imp_NdisSetThreadObjectCompartmentId
0x1400041b7  nop     dword ptr [rax+rax+00h]
0x1400041bc  test    ebx, ebx
0x1400041be  js      short loc_140004147
0x1400041c0  or      byte ptr [rdi+0FAh], 10h
0x1400041c7  mov     r12, [rbp+47h+var_A0]
0x1400041cb  lea     rbx, [rdi+178h]
0x1400041d2  mov     rcx, rbx
0x1400041d5  call    QuicAddrIsWildCard
0x1400041da  test    al, al
0x1400041dc  jz      short loc_14000420B
0x1400041de  test    cs:byte_14005C48B, 4
0x1400041e5  mov     ebx, 0C000000Dh
0x1400041ea  jz      loc_140004147
0x1400041f0  lea     r9, aInvalidWildcar; "Invalid wildcard remote address in conn"...
0x1400041f7  mov     r8, rdi
0x1400041fa  lea     rdx, QuicConnError
0x140004201  call    McTemplateU0ps_EtwWriteTransfer
0x140004206  jmp     loc_140004147
0x14000420b  movzx   eax, [rbp+47h+arg_20]
0x14000420f  ror     ax, 8
0x140004213  mov     [rdi+17Ah], ax
0x14000421a  test    cs:byte_14005C489, 40h
0x140004221  jz      short loc_14000423A
0x140004223  mov     r9b, 1Ch
0x140004226  mov     [rsp+0D0h+var_B0], rbx
0x14000422b  mov     r8, rdi
0x14000422e  lea     rdx, QuicConnRemoteAddrAdded
0x140004235  call    McTemplateU0pubr1_EtwWriteTransfer
0x14000423a  xor     edx, edx; Val
0x14000423c  lea     rcx, [rbp+47h+var_90]; void *
0x140004240  lea     r8d, [rdx+48h]; Size
0x140004244  call    memset
0x140004249  test    byte ptr [rdi+0FAh], 8
0x140004250  jz      short loc_14000425D
0x140004252  lea     rax, [rdi+194h]
0x140004259  mov     [rbp+47h+var_90], rax
0x14000425d  test    byte ptr [rdi+0FCh], 1
0x140004264  mov     [rbp+47h+var_88], rbx
0x140004268  jz      short loc_140004275
0x14000426a  mov     eax, [rdi+1ACh]
0x140004270  mov     [rbp+47h+var_7C], eax
0x140004273  jmp     short loc_140004279
0x140004275  and     [rbp+47h+var_7C], 0
0x140004279  movzx   ecx, word ptr [rdi+10Eh]
0x140004280  call    QuicPartitionIdGetIndex
0x140004285  mov     [rbp+47h+var_78], ax
0x140004289  mov     r14d, 2
0x14000428f  mov     eax, [r12+38h]
0x140004294  test    [rdi+0FBh], r14b
0x14000429b  mov     [rbp+47h+var_68], eax
0x14000429e  mov     rax, [r12+50h]
0x1400042a3  mov     [rbp+47h+var_60], rax
0x1400042a7  lea     eax, [r14-2]
0x1400042ab  cmovnz  eax, r14d
0x1400042af  cmp     byte ptr [rdi+0ECh], 0
0x1400042b6  mov     [rbp+47h+var_80], eax
0x1400042b9  jge     short loc_1400042C1
0x1400042bb  or      eax, 8
0x1400042be  mov     [rbp+47h+var_80], eax
0x1400042c1  mov     cl, [rdi+0EDh]
0x1400042c7  test    cl, 1
0x1400042ca  jz      short loc_1400042D2
0x1400042cc  or      eax, 10h
0x1400042cf  mov     [rbp+47h+var_80], eax
0x1400042d2  test    r14b, cl
0x1400042d5  jz      short loc_1400042DD
0x1400042d7  or      eax, 20h
0x1400042da  mov     [rbp+47h+var_80], eax
0x1400042dd  lea     rdx, [rdi+168h]
0x1400042e4  lea     rcx, [rbp+47h+var_90]
0x1400042e8  call    QuicLibraryGetBinding
0x1400042ed  mov     ebx, eax
0x1400042ef  test    eax, eax
0x1400042f1  js      loc_140004147
0x1400042f7  test    [rdi+0FBh], r14b
0x1400042fe  jz      short loc_14000432A
0x140004300  mov     r9b, [rdi+520h]
0x140004307  lea     rax, [rdi+522h]
0x14000430e  movzx   r8d, word ptr [rdi+10Eh]
0x140004316  xor     edx, edx
0x140004318  mov     rcx, rdi
0x14000431b  mov     [rsp+0D0h+var_B0], rax
0x140004320  call    QuicCidNewRandomSource
0x140004325  mov     rbx, rax
0x140004328  jmp     short loc_140004357
0x14000432a  mov     edx, 38h ; '8'
0x14000432f  mov     r8d, 44306351h
0x140004335  lea     ecx, [rdx+0Ah]
0x140004338  call    cs:__imp_ExAllocatePool2
0x14000433f  nop     dword ptr [rax+rax+00h]
0x140004344  mov     rbx, rax
0x140004347  test    rax, rax
0x14000434a  jz      short loc_140004357
0x14000434c  xorps   xmm0, xmm0
0x14000434f  mov     [rax+20h], rdi
0x140004353  movups  xmmword ptr [rax+28h], xmm0
0x140004357  test    rbx, rbx
0x14000435a  jnz     short loc_140004366
0x14000435c  mov     ebx, 0C0000017h
0x140004361  jmp     loc_140004147
0x140004366  inc     qword ptr [rdi+130h]
0x14000436d  mov     al, cs:byte_14005C48A
0x140004373  test    al, al
0x140004375  jns     short loc_14000439A
0x140004377  mov     r9, [rbx+30h]
0x14000437b  lea     rax, [rbx+38h]
0x14000437f  mov     [rsp+0D0h+var_A8], rax
0x140004384  lea     rdx, QuicConnSourceCidAdded
0x14000438b  mov     al, [rbx+29h]
0x14000438e  mov     r8, rdi
0x140004391  mov     byte ptr [rsp+0D0h+var_B0], al
0x140004395  call    McTemplateU0pxubr2_EtwWriteTransfer
0x14000439a  mov     rax, [rdi+500h]
0x1400043a1  lea     rcx, [rbx+18h]
0x1400043a5  mov     [rcx], rax
0x1400043a8  mov     rdx, rbx
0x1400043ab  mov     [rdi+500h], rcx
0x1400043b2  mov     rcx, [rdi+168h]
0x1400043b9  add     rcx, 40h ; '@'
0x1400043bd  call    QuicLookupAddLocalCid
0x1400043c2  test    al, al
0x1400043c4  jnz     short loc_1400043DC
0x1400043c6  mov     rcx, [rdi+168h]; P
0x1400043cd  call    QuicLibraryReleaseBinding
0x1400043d2  and     qword ptr [rdi+168h], 0
0x1400043da  jmp     short loc_14000435C
0x1400043dc  or      byte ptr [rdi+0FAh], 8
0x1400043e3  lea     rcx, [rdi+194h]
0x1400043ea  mov     rax, [rdi+168h]
0x1400043f1  mov     rax, [rax+20h]
0x1400043f5  movups  xmm0, xmmword ptr [rax]
0x1400043f8  movups  xmmword ptr [rcx], xmm0
0x1400043fb  movsd   xmm1, qword ptr [rax+10h]
0x140004400  movsd   qword ptr [rcx+10h], xmm1
0x140004405  mov     eax, [rax+18h]
0x140004408  mov     [rcx+18h], eax
0x14000440b  test    cs:byte_14005C489, 40h
0x140004412  jz      short loc_14000442B
0x140004414  mov     r9b, 1Ch
0x140004417  mov     [rsp+0D0h+var_B0], rcx
0x14000441c  mov     r8, rdi
0x14000441f  lea     rdx, QuicConnLocalAddrAdded
0x140004426  call    McTemplateU0pubr1_EtwWriteTransfer
0x14000442b  lea     rcx, [rdi+0AE0h]
0x140004432  mov     [rdi+648h], rsi
0x140004439  call    QuicCryptoInitialize
0x14000443e  mov     ebx, eax
0x140004440  test    eax, eax
0x140004442  js      loc_140004164
0x140004448  mov     rdx, r12
0x14000444b  mov     rcx, rdi
0x14000444e  call    QuicConnSetConfiguration
0x140004453  mov     ebx, eax
0x140004455  jmp     loc_140004160
```
