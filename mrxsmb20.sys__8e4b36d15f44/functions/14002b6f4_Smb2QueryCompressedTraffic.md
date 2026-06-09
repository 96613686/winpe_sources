# Smb2QueryCompressedTraffic

- ea: `0x14002b6f4`
- end: `0x14002b8e5`
- name: `Smb2QueryCompressedTraffic`
- size: `497`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001cc00`

## callees

- `0x14002b6f4`
- `0x14002ba20`
- `0x14002ba84`
- `0x1400375c0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14002b7fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002b7fc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b7b4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002b7b4`
- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x14002b836`
- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x14002b836`

## pseudocode

```c
__int64 __fastcall Smb2QueryCompressedTraffic(__int64 a1)
{
  __int64 v1; // rax
  int v2; // r8d
  __int64 v4; // r13
  unsigned int v5; // r15d
  _DWORD *v6; // rdi
  __int64 v7; // rbp
  __int64 v8; // r14
  KIRQL v9; // al
  __int64 v10; // rax
  int v11; // eax
  int v12; // ecx
  int v13; // ecx

  v1 = *(_QWORD *)(a1 + 56);
  v2 = *(_DWORD *)(a1 + 572);
  v4 = *(_QWORD *)(v1 + 136);
  if ( v2 == 64 )
  {
    v5 = 0;
    v6 = *(_DWORD **)(a1 + 560);
    v7 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 56LL);
    memset(v6, 0, 0x40u);
    *v6 = 2;
    v6[1] = 3;
    v8 = *(_QWORD *)(v4 + 96);
    if ( v8 )
    {
      v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 32));
      v6[2] = *(_DWORD *)(v8 + 40);
      *((_QWORD *)v6 + 5) = *(_QWORD *)(v8 + 16);
      *((_QWORD *)v6 + 2) = *(_QWORD *)(v8 + 8);
      *((_QWORD *)v6 + 3) = *(_QWORD *)v8;
      *((_QWORD *)v6 + 4) = *(_QWORD *)(v8 + 24);
      *((_QWORD *)v6 + 6) = *(_QWORD *)(v8 + 48);
      *((_QWORD *)v6 + 7) = *(_QWORD *)(v8 + 56);
      KeReleaseSpinLock((PKSPIN_LOCK)(v8 + 32), v9);
    }
    else
    {
      v10 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 56LL);
      if ( v10 && (*(_DWORD *)(v10 + 4) & 2) != 0
        || !*(_BYTE *)(*(_QWORD *)(a1 + 80) + 1312LL) && (*(_BYTE *)(MRxSmbGetCompressionConfigBlock() + 26) & 1) != 0 )
      {
        v11 = 0;
      }
      else
      {
        v11 = 2;
      }
      v6[2] = v11;
    }
    if ( !v7 )
      goto LABEL_22;
    *v6 = (*(_DWORD *)(v7 + 4) & 2) != 0 ? 1 : -1;
    v12 = *(_DWORD *)(v7 + 48);
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( !v13 )
      {
        v6[1] = 1;
        goto LABEL_22;
      }
      if ( v13 == 1 )
      {
        v6[1] = 2;
LABEL_22:
        *(_QWORD *)(a1 + 184) = 64;
        goto LABEL_23;
      }
    }
    v6[1] = -1;
    goto LABEL_22;
  }
  v5 = -1073741789;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return v5;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_DDq(
      WPP_GLOBAL_Control->AttachedDevice,
      18,
      WPP_65e9b76cb4683fb66828063337b9192b_Traceguids,
      64,
      v2,
      *(_QWORD *)(v1 + 136));
LABEL_23:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_65e9b76cb4683fb66828063337b9192b_Traceguids, v5, v4);
  }
  return v5;
}

```

## disassembly

```asm
0x14002b6f4  push    rbx
0x14002b6f6  push    rbp
0x14002b6f7  push    rsi
0x14002b6f8  push    rdi
0x14002b6f9  push    r13
0x14002b6fb  push    r14
0x14002b6fd  push    r15
0x14002b6ff  sub     rsp, 30h
0x14002b703  mov     rax, [rcx+38h]
0x14002b707  lea     rbx, WPP_GLOBAL_Control
0x14002b70e  mov     r8d, [rcx+23Ch]
0x14002b715  mov     rsi, rcx
0x14002b718  mov     r13, [rax+88h]
0x14002b71f  cmp     r8d, 40h ; '@'
0x14002b723  jz      short loc_14002B77A
0x14002b725  mov     r15d, 0C0000023h
0x14002b72b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b732  cmp     rcx, rbx
0x14002b735  jz      loc_14002B8D2
0x14002b73b  test    dword ptr [rcx+2Ch], 800h
0x14002b742  jz      loc_14002B89A
0x14002b748  cmp     byte ptr [rcx+29h], 4
0x14002b74c  jb      loc_14002B89A
0x14002b752  mov     rcx, [rcx+18h]
0x14002b756  mov     edx, 12h
0x14002b75b  mov     [rsp+68h+var_40], r13
0x14002b760  mov     dword ptr [rsp+68h+var_48], r8d
0x14002b765  lea     r8, WPP_65e9b76cb4683fb66828063337b9192b_Traceguids
0x14002b76c  lea     r9d, [rdx+2Eh]
0x14002b770  call    WPP_SF_DDq
0x14002b775  jmp     loc_14002B89A
0x14002b77a  mov     rax, [rcx+40h]
0x14002b77e  xor     r15d, r15d
0x14002b781  mov     rdi, [rcx+230h]
0x14002b788  xor     edx, edx; Val
0x14002b78a  mov     rcx, rdi; void *
0x14002b78d  mov     rbp, [rax+38h]
0x14002b791  lea     r8d, [r15+40h]; Size
0x14002b795  call    memset
0x14002b79a  mov     dword ptr [rdi], 2
0x14002b7a0  mov     dword ptr [rdi+4], 3
0x14002b7a7  mov     r14, [r13+60h]
0x14002b7ab  test    r14, r14
0x14002b7ae  jz      short loc_14002B811
0x14002b7b0  lea     rcx, [r14+20h]; SpinLock
0x14002b7b4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002b7bb  nop     dword ptr [rax+rax+00h]
0x14002b7c0  mov     dl, al; NewIrql
0x14002b7c2  lea     rcx, [r14+20h]; SpinLock
0x14002b7c6  mov     eax, [r14+28h]
0x14002b7ca  mov     [rdi+8], eax
0x14002b7cd  mov     rax, [r14+10h]
0x14002b7d1  mov     [rdi+28h], rax
0x14002b7d5  mov     rax, [r14+8]
0x14002b7d9  mov     [rdi+10h], rax
0x14002b7dd  mov     rax, [r14]
0x14002b7e0  mov     [rdi+18h], rax
0x14002b7e4  mov     rax, [r14+18h]
0x14002b7e8  mov     [rdi+20h], rax
0x14002b7ec  mov     rax, [r14+30h]
0x14002b7f0  mov     [rdi+30h], rax
0x14002b7f4  mov     rax, [r14+38h]
0x14002b7f8  mov     [rdi+38h], rax
0x14002b7fc  call    cs:__imp_KeReleaseSpinLock
0x14002b803  nop     dword ptr [rax+rax+00h]
0x14002b808  lea     rbx, WPP_GLOBAL_Control
0x14002b80f  jmp     short loc_14002B850
0x14002b811  mov     rax, [rsi+40h]
0x14002b815  mov     rax, [rax+38h]
0x14002b819  test    rax, rax
0x14002b81c  jz      short loc_14002B829
0x14002b81e  mov     eax, [rax+4]
0x14002b821  test    al, 2
0x14002b823  jz      short loc_14002B829
0x14002b825  xor     eax, eax
0x14002b827  jmp     short loc_14002B84D
0x14002b829  mov     rax, [rsi+50h]
0x14002b82d  cmp     [rax+520h], r15b
0x14002b834  jnz     short loc_14002B848
0x14002b836  call    cs:__imp_MRxSmbGetCompressionConfigBlock
0x14002b83d  nop     dword ptr [rax+rax+00h]
0x14002b842  test    byte ptr [rax+1Ah], 1
0x14002b846  jnz     short loc_14002B825
0x14002b848  mov     eax, 2
0x14002b84d  mov     [rdi+8], eax
0x14002b850  test    rbp, rbp
0x14002b853  jz      short loc_14002B88F
0x14002b855  mov     eax, [rbp+4]
0x14002b858  and     al, 2
0x14002b85a  neg     al
0x14002b85c  sbb     ecx, ecx
0x14002b85e  and     ecx, 2
0x14002b861  dec     ecx
0x14002b863  mov     [rdi], ecx
0x14002b865  mov     ecx, [rbp+30h]
0x14002b868  test    ecx, ecx
0x14002b86a  jz      short loc_14002B888
0x14002b86c  sub     ecx, 1
0x14002b86f  jz      short loc_14002B87F
0x14002b871  cmp     ecx, 1
0x14002b874  jnz     short loc_14002B888
0x14002b876  mov     dword ptr [rdi+4], 2
0x14002b87d  jmp     short loc_14002B88F
0x14002b87f  mov     dword ptr [rdi+4], 1
0x14002b886  jmp     short loc_14002B88F
0x14002b888  mov     dword ptr [rdi+4], 0FFFFFFFFh
0x14002b88f  mov     qword ptr [rsi+0B8h], 40h ; '@'
0x14002b89a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b8a1  cmp     rcx, rbx
0x14002b8a4  jz      short loc_14002B8D2
0x14002b8a6  test    dword ptr [rcx+2Ch], 800h
0x14002b8ad  jz      short loc_14002B8D2
0x14002b8af  cmp     byte ptr [rcx+29h], 4
0x14002b8b3  jb      short loc_14002B8D2
0x14002b8b5  mov     rcx, [rcx+18h]
0x14002b8b9  lea     r8, WPP_65e9b76cb4683fb66828063337b9192b_Traceguids
0x14002b8c0  mov     edx, 13h
0x14002b8c5  mov     [rsp+68h+var_48], r13
0x14002b8ca  mov     r9d, r15d
0x14002b8cd  call    WPP_SF_dq
0x14002b8d2  mov     eax, r15d
0x14002b8d5  add     rsp, 30h
0x14002b8d9  pop     r15
0x14002b8db  pop     r14
0x14002b8dd  pop     r13
0x14002b8df  pop     rdi
0x14002b8e0  pop     rsi
0x14002b8e1  pop     rbp
0x14002b8e2  pop     rbx
0x14002b8e3  retn
```
