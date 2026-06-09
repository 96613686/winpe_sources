# Smb2SessionSetup_CopyData

- ea: `0x14002e780`
- end: `0x14002e97d`
- name: `Smb2SessionSetup_CopyData`
- size: `509`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14002a040`
- `0x14002e780`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002e7e7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002e7e7`
- `mrxsmb!SmbCryptoUpdatePreauthIntegrityHashValue` at `0x14002e815`
- `mrxsmb!SmbCryptoUpdatePreauthIntegrityHashValue` at `0x14002e8ca`
- `mrxsmb!SmbCryptoUpdatePreauthIntegrityHashValue` at `0x14002e815`
- `mrxsmb!SmbCryptoUpdatePreauthIntegrityHashValue` at `0x14002e8ca`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14002e964`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14002e964`
- `mrxsmb!SmbCeContinueExchange` at `0x14002e940`
- `mrxsmb!SmbCeContinueExchange` at `0x14002e940`

## pseudocode

```c
__int64 __fastcall Smb2SessionSetup_CopyData(__int64 a1, __int64 a2, unsigned int a3, int a4)
{
  int updated; // ebx
  __int64 v7; // rcx
  PVOID v8; // r9
  __int64 v9; // rcx

  if ( a4 >= 0 )
  {
    if ( a3 < *(_DWORD *)(a2 + 748) )
    {
      updated = -1073741629;
LABEL_23:
      SmbCseUpdateBufferContextStatus(a2, (unsigned int)updated);
      return 0;
    }
    updated = 0;
    if ( *(_QWORD *)(a1 + 1032) )
    {
      v7 = *(_QWORD *)(a2 + 96);
      if ( (*(_BYTE *)(v7 + 10) & 5) != 0 )
        v8 = *(PVOID *)(v7 + 24);
      else
        v8 = MmMapLockedPagesSpecifyCache((PMDL)v7, 0, MmCached, 0, 0, 0x40000010u);
      updated = SmbCryptoUpdatePreauthIntegrityHashValue(
                  *(_QWORD *)(a1 + 1032),
                  *(_QWORD *)(a1 + 1040),
                  *(unsigned int *)(a1 + 1048),
                  v8,
                  *(_DWORD *)(a2 + 728));
      if ( updated < 0 )
        goto LABEL_9;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_DDqq(
          WPP_GLOBAL_Control->AttachedDevice,
          40,
          WPP_981a12f1532a3df13e243e2e48204374_Traceguids,
          **(unsigned int **)(a1 + 1040),
          *(_DWORD *)(a2 + 728),
          *(_QWORD *)(a1 + 80),
          *(_QWORD *)(*(_QWORD *)(a1 + 96) + 392LL));
      }
    }
    if ( *(_DWORD *)(a2 + 48) == -1073741802 )
    {
      v9 = *(_QWORD *)(a1 + 1032);
      if ( v9 )
      {
        updated = SmbCryptoUpdatePreauthIntegrityHashValue(
                    v9,
                    *(_QWORD *)(a1 + 1040),
                    *(unsigned int *)(a1 + 1048),
                    *(_QWORD *)(a2 + 712),
                    *(_DWORD *)(a2 + 748));
        if ( updated < 0 )
        {
LABEL_9:
          updated = -1073741595;
          goto LABEL_23;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_DDqq(
            WPP_GLOBAL_Control->AttachedDevice,
            41,
            WPP_981a12f1532a3df13e243e2e48204374_Traceguids,
            **(unsigned int **)(a1 + 1040),
            *(_DWORD *)(a2 + 748),
            *(_QWORD *)(a1 + 80),
            *(_QWORD *)(*(_QWORD *)(a1 + 96) + 392LL));
        }
      }
      SmbCeContinueExchange(a1);
    }
    if ( updated < 0 )
      goto LABEL_23;
  }
  return 0;
}

```

## disassembly

```asm
0x14002e780  push    rbx
0x14002e782  push    rsi
0x14002e783  push    rdi
0x14002e784  push    r14
0x14002e786  sub     rsp, 48h
0x14002e78a  mov     rsi, rdx
0x14002e78d  mov     rdi, rcx
0x14002e790  test    r9d, r9d
0x14002e793  js      loc_14002E970
0x14002e799  cmp     r8d, [rdx+2ECh]
0x14002e7a0  jnb     short loc_14002E7AC
0x14002e7a2  mov     ebx, 0C00000C3h
0x14002e7a7  jmp     loc_14002E950
0x14002e7ac  xor     ebx, ebx
0x14002e7ae  lea     r14, WPP_GLOBAL_Control
0x14002e7b5  cmp     [rcx+408h], rbx
0x14002e7bc  jz      loc_14002E88E
0x14002e7c2  mov     rcx, [rdx+60h]; MemoryDescriptorList
0x14002e7c6  test    byte ptr [rcx+0Ah], 5
0x14002e7ca  jz      short loc_14002E7D2
0x14002e7cc  mov     r9, [rcx+18h]
0x14002e7d0  jmp     short loc_14002E7F6
0x14002e7d2  xor     r9d, r9d; RequestedAddress
0x14002e7d5  mov     [rsp+68h+Priority], 40000010h; Priority
0x14002e7dd  xor     edx, edx; AccessMode
0x14002e7df  mov     [rsp+68h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x14002e7e3  lea     r8d, [r9+1]; CacheType
0x14002e7e7  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002e7ee  nop     dword ptr [rax+rax+00h]
0x14002e7f3  mov     r9, rax
0x14002e7f6  mov     eax, [rsi+2D8h]
0x14002e7fc  mov     r8d, [rdi+418h]
0x14002e803  mov     rdx, [rdi+410h]
0x14002e80a  mov     rcx, [rdi+408h]
0x14002e811  mov     [rsp+68h+BugCheckOnFailure], eax
0x14002e815  call    cs:__imp_SmbCryptoUpdatePreauthIntegrityHashValue
0x14002e81c  nop     dword ptr [rax+rax+00h]
0x14002e821  mov     ebx, eax
0x14002e823  test    eax, eax
0x14002e825  jns     short loc_14002E831
0x14002e827  mov     ebx, 0C00000E5h
0x14002e82c  jmp     loc_14002E950
0x14002e831  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002e838  cmp     rcx, r14
0x14002e83b  jz      short loc_14002E88E
0x14002e83d  test    dword ptr [rcx+2Ch], 400h
0x14002e844  jz      short loc_14002E88E
0x14002e846  cmp     byte ptr [rcx+29h], 4
0x14002e84a  jb      short loc_14002E88E
0x14002e84c  mov     rax, [rdi+60h]
0x14002e850  lea     r8, WPP_981a12f1532a3df13e243e2e48204374_Traceguids
0x14002e857  mov     r9, [rdi+410h]
0x14002e85e  mov     edx, 28h ; '('
0x14002e863  mov     rcx, [rcx+18h]
0x14002e867  mov     rax, [rax+188h]
0x14002e86e  mov     r9d, [r9]
0x14002e871  mov     [rsp+68h+var_38], rax
0x14002e876  mov     rax, [rdi+50h]
0x14002e87a  mov     qword ptr [rsp+68h+Priority], rax
0x14002e87f  mov     eax, [rsi+2D8h]
0x14002e885  mov     [rsp+68h+BugCheckOnFailure], eax
0x14002e889  call    WPP_SF_DDqq
0x14002e88e  cmp     dword ptr [rsi+30h], 0C0000016h
0x14002e895  jnz     loc_14002E94C
0x14002e89b  mov     rcx, [rdi+408h]
0x14002e8a2  test    rcx, rcx
0x14002e8a5  jz      loc_14002E93D
0x14002e8ab  mov     eax, [rsi+2ECh]
0x14002e8b1  mov     r9, [rsi+2C8h]
0x14002e8b8  mov     r8d, [rdi+418h]
0x14002e8bf  mov     rdx, [rdi+410h]
0x14002e8c6  mov     [rsp+68h+BugCheckOnFailure], eax
0x14002e8ca  call    cs:__imp_SmbCryptoUpdatePreauthIntegrityHashValue
0x14002e8d1  nop     dword ptr [rax+rax+00h]
0x14002e8d6  mov     ebx, eax
0x14002e8d8  test    eax, eax
0x14002e8da  js      loc_14002E827
0x14002e8e0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002e8e7  cmp     rcx, r14
0x14002e8ea  jz      short loc_14002E93D
0x14002e8ec  test    dword ptr [rcx+2Ch], 400h
0x14002e8f3  jz      short loc_14002E93D
0x14002e8f5  cmp     byte ptr [rcx+29h], 4
0x14002e8f9  jb      short loc_14002E93D
0x14002e8fb  mov     rax, [rdi+60h]
0x14002e8ff  lea     r8, WPP_981a12f1532a3df13e243e2e48204374_Traceguids
0x14002e906  mov     r9, [rdi+410h]
0x14002e90d  mov     edx, 29h ; ')'
0x14002e912  mov     rcx, [rcx+18h]
0x14002e916  mov     rax, [rax+188h]
0x14002e91d  mov     r9d, [r9]
0x14002e920  mov     [rsp+68h+var_38], rax
0x14002e925  mov     rax, [rdi+50h]
0x14002e929  mov     qword ptr [rsp+68h+Priority], rax
0x14002e92e  mov     eax, [rsi+2ECh]
0x14002e934  mov     [rsp+68h+BugCheckOnFailure], eax
0x14002e938  call    WPP_SF_DDqq
0x14002e93d  mov     rcx, rdi
0x14002e940  call    cs:__imp_SmbCeContinueExchange
0x14002e947  nop     dword ptr [rax+rax+00h]
0x14002e94c  test    ebx, ebx
0x14002e94e  jns     short loc_14002E970
0x14002e950  mov     dword ptr [rsp+68h+arg_0], ebx
0x14002e954  mov     rcx, rsi
0x14002e957  mov     dword ptr [rsp+68h+arg_0+4], 0
0x14002e95f  mov     rdx, [rsp+68h+arg_0]
0x14002e964  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x14002e96b  nop     dword ptr [rax+rax+00h]
0x14002e970  xor     eax, eax
0x14002e972  add     rsp, 48h
0x14002e976  pop     r14
0x14002e978  pop     rdi
0x14002e979  pop     rsi
0x14002e97a  pop     rbx
0x14002e97b  retn
```
