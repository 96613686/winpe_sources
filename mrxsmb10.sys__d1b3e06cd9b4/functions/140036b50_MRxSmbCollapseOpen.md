# MRxSmbCollapseOpen

- ea: `0x140036b50`
- end: `0x140036c94`
- name: `MRxSmbCollapseOpen`
- size: `324`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000dc44`
- `0x140036b50`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140036bfd`
- `ntoskrnl!ExAllocatePool2` at `0x140036bfd`
- `rdbss!RxCreateNetFobx` at `0x140036b72`
- `rdbss!RxCreateNetFobx` at `0x140036b72`

## pseudocode

```c
__int64 __fastcall MRxSmbCollapseOpen(struct _RX_CONTEXT *a1)
{
  PMRX_FOBX pFobx; // rax
  struct _MRX_SRV_OPEN_ *pRelevantSrvOpen; // rbx
  unsigned int v4; // esi
  PMRX_FOBX v5; // rbx
  PMRX_FOBX v6; // r9
  _DWORD *FileName; // rdx

  pFobx = a1->pFobx;
  if ( pFobx
    || (pRelevantSrvOpen = a1->pRelevantSrvOpen, pFobx = RxCreateNetFobx(a1, pRelevantSrvOpen), (a1->pFobx = pFobx) != 0) )
  {
    LODWORD(pFobx[1].Context) = 1;
    v4 = 0;
    if ( !a1->pFobx->UnicodeQueryTemplate.Buffer )
    {
      v5 = a1->pFobx;
      v5->UnicodeQueryTemplate.Buffer = (PWSTR)ExAllocatePool2(256, 72, 1766223187);
      v6 = a1->pFobx;
      if ( !v6->UnicodeQueryTemplate.Buffer )
      {
        v4 = -1073741670;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
        {
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            26,
            WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
            v6,
            -1073741670);
        }
      }
      FileName = a1->TrackerHistory[1].FileName;
      if ( FileName )
      {
        if ( ((FileName[2] - 2) & 0xFFFFFFFD) == 0 )
          FileName[5] = 2;
        if ( (FileName[3] & 8) != 0 )
          FileName[6] |= 8u;
      }
    }
  }
  else
  {
    v4 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
        pRelevantSrvOpen,
        -1073741670);
  }
  return v4;
}

```

## disassembly

```asm
0x140036b50  mov     [rsp+arg_0], rbx
0x140036b55  mov     [rsp+arg_8], rsi
0x140036b5a  push    rdi
0x140036b5b  sub     rsp, 30h
0x140036b5f  mov     rax, [rcx+40h]
0x140036b63  mov     rdi, rcx
0x140036b66  test    rax, rax
0x140036b69  jnz     short loc_140036BD5
0x140036b6b  mov     rbx, [rcx+48h]
0x140036b6f  mov     rdx, rbx; MrxSrvOpen
0x140036b72  call    cs:__imp_RxCreateNetFobx
0x140036b79  nop     dword ptr [rax+rax+00h]
0x140036b7e  mov     [rdi+40h], rax
0x140036b82  test    rax, rax
0x140036b85  jnz     short loc_140036BD5
0x140036b87  mov     esi, 0C000009Ah
0x140036b8c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140036b93  lea     rax, WPP_GLOBAL_Control
0x140036b9a  cmp     rcx, rax
0x140036b9d  jz      loc_140036C81
0x140036ba3  test    dword ptr [rcx+2Ch], 100h
0x140036baa  jz      loc_140036C81
0x140036bb0  mov     rcx, [rcx+18h]
0x140036bb4  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140036bbb  mov     edx, 1Bh
0x140036bc0  mov     [rsp+38h+var_18], 0C000009Ah
0x140036bc8  mov     r9, rbx
0x140036bcb  call    WPP_SF_qD
0x140036bd0  jmp     loc_140036C81
0x140036bd5  mov     dword ptr [rax+60h], 1
0x140036bdc  xor     esi, esi
0x140036bde  mov     rax, [rdi+40h]
0x140036be2  cmp     [rax+38h], rsi
0x140036be6  jnz     loc_140036C81
0x140036bec  lea     edx, [rsi+48h]
0x140036bef  mov     ecx, 100h
0x140036bf4  mov     r8d, 69466D53h
0x140036bfa  mov     rbx, rax
0x140036bfd  call    cs:__imp_ExAllocatePool2
0x140036c04  nop     dword ptr [rax+rax+00h]
0x140036c09  mov     [rbx+38h], rax
0x140036c0d  mov     r9, [rdi+40h]
0x140036c11  cmp     [r9+38h], rsi
0x140036c15  jnz     short loc_140036C55
0x140036c17  mov     esi, 0C000009Ah
0x140036c1c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140036c23  lea     rax, WPP_GLOBAL_Control
0x140036c2a  cmp     rcx, rax
0x140036c2d  jz      short loc_140036C55
0x140036c2f  test    dword ptr [rcx+2Ch], 100h
0x140036c36  jz      short loc_140036C55
0x140036c38  mov     rcx, [rcx+18h]
0x140036c3c  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140036c43  mov     edx, 1Ah
0x140036c48  mov     [rsp+38h+var_18], 0C000009Ah
0x140036c50  call    WPP_SF_qD
0x140036c55  mov     rdx, [rdi+2A0h]
0x140036c5c  test    rdx, rdx
0x140036c5f  jz      short loc_140036C81
0x140036c61  mov     eax, [rdx+8]
0x140036c64  sub     eax, 2
0x140036c67  test    eax, 0FFFFFFFDh
0x140036c6c  jnz     short loc_140036C75
0x140036c6e  mov     dword ptr [rdx+14h], 2
0x140036c75  mov     ecx, [rdx+0Ch]
0x140036c78  test    cl, 8
0x140036c7b  jz      short loc_140036C81
0x140036c7d  or      dword ptr [rdx+18h], 8
0x140036c81  mov     rbx, [rsp+38h+arg_0]
0x140036c86  mov     eax, esi
0x140036c88  mov     rsi, [rsp+38h+arg_8]
0x140036c8d  add     rsp, 30h
0x140036c91  pop     rdi
0x140036c92  retn
```
