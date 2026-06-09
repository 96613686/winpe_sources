# PassNamePduToWins

- ea: `0x140052864`
- end: `0x140052b02`
- name: `PassNamePduToWins`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140009150`

## callees

- `0x140004880`
- `0x140031140`
- `0x140040294`
- `0x140040428`
- `0x140041e1c`
- `0x140052864`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140052a2c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140052a2c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400528c9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400528c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400529e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052ae1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400529e1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140052ae1`
- `ntoskrnl!ExAllocatePool2` at `0x14005291d`
- `ntoskrnl!ExAllocatePool2` at `0x14005291d`

## pseudocode

```c
__int64 __fastcall PassNamePduToWins(__int64 a1, __int64 a2, _BYTE *a3, unsigned int a4)
{
  size_t v4; // rsi
  __int16 v6; // r13
  KIRQL v7; // al
  KIRQL v8; // di
  IRP *v9; // r14
  unsigned int v10; // r12d
  __int64 Pool2; // rax
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 *v15; // rcx
  PMDL MdlAddress; // rcx
  unsigned __int64 ByteCount; // rdi
  _WORD *MappedSystemVa; // rbx
  unsigned int v19; // edi
  NTSTATUS v20; // ebx
  int v22; // [rsp+30h] [rbp-58h]
  __int16 v23; // [rsp+98h] [rbp+10h]

  v4 = a4;
  v23 = *(_WORD *)(a2 + 8);
  v22 = *(_DWORD *)(a2 + 10);
  v6 = 2;
  if ( (BYTE3(xmmword_140038420) & 2) != 0 )
    WPP_SF_qdd(
      1049,
      18,
      WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids,
      a1,
      *(_DWORD *)(a2 + 10),
      *(__int16 *)(a2 + 8));
  v7 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  v8 = v7;
  if ( !pWinsInfo )
    goto LABEL_30;
  v9 = *(IRP **)(pWinsInfo + 64);
  v10 = 0;
  if ( !v9 )
  {
    if ( *(_DWORD *)(pWinsInfo + 72) < *(_DWORD *)(pWinsInfo + 76) )
    {
      if ( (unsigned int)v4 < 0xFFFFFFD8 && (_DWORD)v4 != 0 )
      {
        Pool2 = ExAllocatePool2(64, (unsigned int)(v4 + 40), 1987338830);
        v12 = Pool2;
        if ( Pool2 )
        {
          if ( a3[7] == 0xFF )
          {
            a3[7] = 0;
            v6 = 1;
          }
          *(_WORD *)(Pool2 + 20) = v6;
          memmove((void *)(Pool2 + 32), a3, v4);
          v13 = pWinsInfo;
          *(_WORD *)(v12 + 22) = v23;
          *(_DWORD *)(v12 + 24) = v22;
          *(_DWORD *)(v12 + 16) = v4 + 12;
          *(_DWORD *)(v12 + 28) = v4;
          *(_DWORD *)(v13 + 72) += v4 + 12;
          if ( (BYTE2(xmmword_140038420) & 1) != 0 )
            WPP_SF_(1040, 19, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids);
          v14 = pWinsInfo + 24;
          v15 = *(__int64 **)(pWinsInfo + 32);
          if ( *v15 != pWinsInfo + 24 )
            __fastfail(3u);
          *(_QWORD *)v12 = v14;
          *(_QWORD *)(v12 + 8) = v15;
          *v15 = v12;
          *(_QWORD *)(v14 + 8) = v12;
        }
      }
      goto LABEL_31;
    }
LABEL_30:
    v10 = -1073741670;
LABEL_31:
    KeReleaseSpinLock(&SpinLock, v8);
    return v10;
  }
  *(_QWORD *)(pWinsInfo + 64) = 0;
  KeReleaseSpinLock(&SpinLock, v7);
  MdlAddress = v9->MdlAddress;
  if ( MdlAddress
    && (ByteCount = MdlAddress->ByteCount, (unsigned int)ByteCount >= 0xC)
    && ((MdlAddress->MdlFlags & 5) == 0
      ? (MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000020u))
      : (MappedSystemVa = MdlAddress->MappedSystemVa),
        MappedSystemVa) )
  {
    if ( ByteCount < v4 + 12 )
      v19 = ByteCount - 12;
    else
      v19 = v4;
    if ( a3[7] == 0xFF )
    {
      a3[7] = 0;
      v6 = 1;
    }
    *MappedSystemVa = v6;
    memmove(MappedSystemVa + 6, a3, v19);
    MappedSystemVa[1] = v23;
    *((_DWORD *)MappedSystemVa + 1) = v22;
    *((_DWORD *)MappedSystemVa + 2) = v4;
    v20 = v19 < (unsigned int)v4 ? 0x80000005 : 0;
    if ( (BYTE2(xmmword_140038420) & 1) != 0 )
      WPP_SF_dq(1040, 20, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids, (unsigned int)v4, v9);
  }
  else
  {
    v20 = -1073741670;
    v19 = 0;
  }
  NTIoComplete(v9, v20, v19);
  return v10;
}

```

## disassembly

```asm
0x140052864  push    rbx
0x140052866  push    rbp
0x140052867  push    rsi
0x140052868  push    rdi
0x140052869  push    r12
0x14005286b  push    r13
0x14005286d  push    r14
0x14005286f  push    r15
0x140052871  sub     rsp, 48h
0x140052875  mov     esi, r9d
0x140052878  mov     r15, r8
0x14005287b  mov     r8d, [rdx+0Ah]
0x14005287f  mov     r9, rcx
0x140052882  movsx   ecx, word ptr [rdx+8]
0x140052886  mov     [rsp+88h+arg_8], cx
0x14005288e  mov     [rsp+88h+var_58], r8d
0x140052893  mov     r13d, 2
0x140052899  test    byte ptr cs:xmmword_140038420+3, r13b
0x1400528a0  jz      short loc_1400528C2
0x1400528a2  mov     eax, ecx
0x1400528a4  lea     edx, [r13+10h]
0x1400528a8  mov     [rsp+88h+Priority], eax
0x1400528ac  mov     ecx, 419h
0x1400528b1  mov     [rsp+88h+BugCheckOnFailure], r8d
0x1400528b6  lea     r8, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids
0x1400528bd  call    WPP_SF_qdd
0x1400528c2  lea     rcx, SpinLock; SpinLock
0x1400528c9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400528d0  nop     dword ptr [rax+rax+00h]
0x1400528d5  mov     rdx, cs:pWinsInfo
0x1400528dc  mov     dil, al
0x1400528df  test    rdx, rdx
0x1400528e2  jz      loc_140052AD1
0x1400528e8  mov     r14, [rdx+40h]
0x1400528ec  xor     r12d, r12d
0x1400528ef  test    r14, r14
0x1400528f2  jnz     loc_1400529D3
0x1400528f8  mov     ecx, [rdx+4Ch]
0x1400528fb  cmp     [rdx+48h], ecx
0x1400528fe  jnb     loc_140052AD1
0x140052904  lea     eax, [rsi+28h]
0x140052907  cmp     eax, 28h ; '('
0x14005290a  jbe     loc_140052AD7
0x140052910  mov     edx, eax
0x140052912  lea     ecx, [r12+40h]
0x140052917  mov     r8d, 7674624Eh
0x14005291d  call    cs:__imp_ExAllocatePool2
0x140052924  nop     dword ptr [rax+rax+00h]
0x140052929  mov     rbx, rax
0x14005292c  test    rax, rax
0x14005292f  jz      loc_140052AD7
0x140052935  cmp     byte ptr [r15+7], 0FFh
0x14005293a  lea     ebp, [r12+1]
0x14005293f  jnz     short loc_140052949
0x140052941  mov     [r15+7], r12b
0x140052945  movzx   r13d, bp
0x140052949  mov     r8, rsi; Size
0x14005294c  mov     [rax+14h], r13w
0x140052951  lea     rcx, [rax+20h]; void *
0x140052955  mov     rdx, r15; Src
0x140052958  call    memmove
0x14005295d  movzx   eax, [rsp+88h+arg_8]
0x140052965  mov     rcx, cs:pWinsInfo
0x14005296c  mov     [rbx+16h], ax
0x140052970  mov     eax, [rsp+88h+var_58]
0x140052974  mov     [rbx+18h], eax
0x140052977  lea     eax, [rsi+0Ch]
0x14005297a  mov     [rbx+10h], eax
0x14005297d  lea     eax, [rsi+0Ch]
0x140052980  mov     [rbx+1Ch], esi
0x140052983  add     [rcx+48h], eax
0x140052986  test    byte ptr cs:xmmword_140038420+2, bpl
0x14005298d  jz      short loc_1400529A5
0x14005298f  mov     edx, 13h
0x140052994  lea     r8, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids
0x14005299b  mov     ecx, 410h
0x1400529a0  call    WPP_SF_
0x1400529a5  mov     rax, cs:pWinsInfo
0x1400529ac  add     rax, 18h
0x1400529b0  mov     rcx, [rax+8]
0x1400529b4  cmp     [rcx], rax
0x1400529b7  jz      short loc_1400529C0
0x1400529b9  mov     ecx, 3
0x1400529be  int     29h; Win8: RtlFailFast(ecx)
0x1400529c0  mov     [rbx], rax
0x1400529c3  mov     [rbx+8], rcx
0x1400529c7  mov     [rcx], rbx
0x1400529ca  mov     [rax+8], rbx
0x1400529ce  jmp     loc_140052AD7
0x1400529d3  mov     [rdx+40h], r12
0x1400529d7  lea     rcx, SpinLock; SpinLock
0x1400529de  mov     dl, dil; NewIrql
0x1400529e1  call    cs:__imp_KeReleaseSpinLock
0x1400529e8  nop     dword ptr [rax+rax+00h]
0x1400529ed  mov     rcx, [r14+8]; MemoryDescriptorList
0x1400529f1  test    rcx, rcx
0x1400529f4  jz      loc_140052ABB
0x1400529fa  mov     edi, [rcx+28h]
0x1400529fd  cmp     edi, 0Ch
0x140052a00  jb      loc_140052ABB
0x140052a06  test    byte ptr [rcx+0Ah], 5
0x140052a0a  mov     ebp, 1
0x140052a0f  jz      short loc_140052A17
0x140052a11  mov     rbx, [rcx+18h]
0x140052a15  jmp     short loc_140052A3B
0x140052a17  mov     [rsp+88h+Priority], 40000020h; Priority
0x140052a1f  xor     r9d, r9d; RequestedAddress
0x140052a22  mov     r8d, ebp; CacheType
0x140052a25  mov     [rsp+88h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x140052a2a  xor     edx, edx; AccessMode
0x140052a2c  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140052a33  nop     dword ptr [rax+rax+00h]
0x140052a38  mov     rbx, rax
0x140052a3b  test    rbx, rbx
0x140052a3e  jz      short loc_140052ABB
0x140052a40  lea     rdx, [rsi+0Ch]
0x140052a44  cmp     rdi, rdx
0x140052a47  jb      short loc_140052A4D
0x140052a49  mov     edi, esi
0x140052a4b  jmp     short loc_140052A50
0x140052a4d  add     edi, 0FFFFFFF4h
0x140052a50  cmp     byte ptr [r15+7], 0FFh
0x140052a55  jnz     short loc_140052A5F
0x140052a57  mov     [r15+7], r12b
0x140052a5b  movzx   r13d, bp
0x140052a5f  mov     r8d, edi; Size
0x140052a62  lea     rcx, [rbx+0Ch]; void *
0x140052a66  mov     rdx, r15; Src
0x140052a69  mov     [rbx], r13w
0x140052a6d  call    memmove
0x140052a72  movzx   eax, [rsp+88h+arg_8]
0x140052a7a  mov     [rbx+2], ax
0x140052a7e  mov     eax, [rsp+88h+var_58]
0x140052a82  mov     [rbx+4], eax
0x140052a85  mov     [rbx+8], esi
0x140052a88  cmp     edi, esi
0x140052a8a  sbb     ebx, ebx
0x140052a8c  and     ebx, 80000005h
0x140052a92  test    byte ptr cs:xmmword_140038420+2, bpl
0x140052a99  jz      short loc_140052AC2
0x140052a9b  mov     edx, 14h
0x140052aa0  mov     qword ptr [rsp+88h+BugCheckOnFailure], r14
0x140052aa5  mov     ecx, 410h
0x140052aaa  lea     r8, WPP_444b716a43e9321e54c6bf40e13ea9af_Traceguids
0x140052ab1  mov     r9d, esi
0x140052ab4  call    WPP_SF_dq
0x140052ab9  jmp     short loc_140052AC2
0x140052abb  mov     ebx, 0C000009Ah
0x140052ac0  xor     edi, edi
0x140052ac2  mov     r8d, edi
0x140052ac5  mov     edx, ebx
0x140052ac7  mov     rcx, r14; Irp
0x140052aca  call    NTIoComplete
0x140052acf  jmp     short loc_140052AED
0x140052ad1  mov     r12d, 0C000009Ah
0x140052ad7  mov     dl, dil; NewIrql
0x140052ada  lea     rcx, SpinLock; SpinLock
0x140052ae1  call    cs:__imp_KeReleaseSpinLock
0x140052ae8  nop     dword ptr [rax+rax+00h]
0x140052aed  mov     eax, r12d
0x140052af0  add     rsp, 48h
0x140052af4  pop     r15
0x140052af6  pop     r14
0x140052af8  pop     r13
0x140052afa  pop     r12
0x140052afc  pop     rdi
0x140052afd  pop     rsi
0x140052afe  pop     rbp
0x140052aff  pop     rbx
0x140052b00  retn
```
