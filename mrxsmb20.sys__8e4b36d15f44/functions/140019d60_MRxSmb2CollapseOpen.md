# MRxSmb2CollapseOpen

- ea: `0x140019d60`
- end: `0x140019fd0`
- name: `MRxSmb2CollapseOpen`
- size: `624`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140019d60`
- `0x140019fe0`
- `0x140029764`
- `0x140029840`
- `0x14002a780`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140019ee1`
- `ntoskrnl!ExAllocatePool2` at `0x140019ee1`
- `rdbss!RxCreateNetFobx` at `0x140019d93`
- `rdbss!RxCreateNetFobx` at `0x140019d93`
- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x140019e18`
- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x140019e2a`
- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x140019e18`
- `mrxsmb!MRxSmbGetCompressionConfigBlock` at `0x140019e2a`

## pseudocode

```c
__int64 __fastcall MRxSmb2CollapseOpen(PRX_CONTEXT RxContext)
{
  PMRX_SRV_OPEN pRelevantSrvOpen; // rdi
  PMRX_FCB pFcb; // r15
  PMRX_FOBX pFobx; // rcx
  __int64 v5; // rbp
  PMRX_SHADOW_CALLDOWN DispatchRoutine; // rsi
  struct _MRX_FOBX_ *NetFobx; // rax
  PMRX_FOBX v8; // rdi
  PSZ FileName; // rcx
  unsigned int v10; // edi
  int v11; // eax
  int v12; // ecx
  int v13; // eax
  WCHAR *Pool2; // rax

  pRelevantSrvOpen = RxContext->pRelevantSrvOpen;
  pFcb = RxContext->pFcb;
  pFobx = RxContext->pFobx;
  v5 = *(_QWORD *)&pRelevantSrvOpen->Flags;
  DispatchRoutine = pRelevantSrvOpen->ShadowContext->DispatchRoutine;
  if ( pFobx
    || (NetFobx = RxCreateNetFobx(RxContext, pRelevantSrvOpen),
        RxContext->pFobx = NetFobx,
        LOBYTE(pFobx) = (_BYTE)NetFobx,
        NetFobx) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqqZ(
        WPP_GLOBAL_Control->AttachedDevice,
        46,
        (unsigned int)WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
        (_DWORD)pFcb,
        (char)pRelevantSrvOpen,
        (char)pFobx,
        *(_QWORD *)&pRelevantSrvOpen->DesiredAccess);
    }
    LODWORD(RxContext->pFobx[1].Context) = 0;
    v8 = RxContext->pFobx;
    if ( v8->UnicodeQueryTemplate.Buffer )
      goto LABEL_6;
    Pool2 = (WCHAR *)ExAllocatePool2(256, 56, 1834182982);
    if ( Pool2 )
    {
      *Pool2 = -7136;
      v8->UnicodeQueryTemplate.Buffer = Pool2;
LABEL_6:
      FileName = RxContext->TrackerHistory[1].FileName;
      v10 = 0;
      if ( FileName )
      {
        v11 = *(_DWORD *)(v5 + 8);
        if ( (v11 & 0x400) != 0 )
        {
          *((_DWORD *)FileName + 5) = 3;
        }
        else if ( (v11 & 0x200) != 0 )
        {
          *((_DWORD *)FileName + 5) = 2;
        }
        if ( (*((_DWORD *)FileName + 3) & 8) != 0 )
          *((_DWORD *)FileName + 6) |= 8u;
      }
      if ( (*(_BYTE *)(MRxSmbGetCompressionConfigBlock() + 26) & 2) == 0 )
      {
        if ( (*(_BYTE *)(MRxSmbGetCompressionConfigBlock() + 26) & 1) != 0
          && !*(_BYTE *)(*((_QWORD *)DispatchRoutine + 3) + 1312LL)
          || (v12 = *(_DWORD *)(v5 + 324), v12 != -1)
          && (v13 = *((_DWORD *)DispatchRoutine + 119), v13 != -1)
          && (v13 == 1 || v12 == 1 || (*(_DWORD *)(*((_QWORD *)DispatchRoutine + 53) + 180LL) & 0x80000) != 0) )
        {
          Smb2EnableCompressionForFobx((__int64)RxContext->pFobx, 0);
        }
      }
      return v10;
    }
    v10 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        47,
        WPP_584f9b0e749e3be8080bab44300b7711_Traceguids,
        RxContext->pFobx,
        -1073741670);
    }
  }
  else
  {
    v10 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids, 3221225626LL);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x140019d60  push    rbx
0x140019d62  push    rbp
0x140019d63  push    rsi
0x140019d64  push    rdi
0x140019d65  push    r14
0x140019d67  push    r15
0x140019d69  sub     rsp, 48h
0x140019d6d  mov     rdi, [rcx+48h]
0x140019d71  mov     rbx, rcx
0x140019d74  mov     r15, [rcx+38h]
0x140019d78  mov     rcx, [rcx+40h]
0x140019d7c  mov     rax, [rdi+28h]
0x140019d80  mov     rbp, [rdi+30h]
0x140019d84  mov     rsi, [rax+28h]
0x140019d88  test    rcx, rcx
0x140019d8b  jnz     short loc_140019DAF
0x140019d8d  mov     rdx, rdi; MrxSrvOpen
0x140019d90  mov     rcx, rbx; RxContext
0x140019d93  call    cs:__imp_RxCreateNetFobx
0x140019d9a  nop     dword ptr [rax+rax+00h]
0x140019d9f  mov     [rbx+40h], rax
0x140019da3  mov     rcx, rax
0x140019da6  test    rax, rax
0x140019da9  jz      loc_140019E8F
0x140019daf  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140019db6  lea     r14, WPP_GLOBAL_Control
0x140019dbd  cmp     r10, r14
0x140019dc0  jz      short loc_140019DCE
0x140019dc2  mov     eax, [r10+2Ch]
0x140019dc6  test    al, 20h
0x140019dc8  jnz     loc_140019F30
0x140019dce  mov     rax, [rbx+40h]
0x140019dd2  mov     dword ptr [rax+60h], 0
0x140019dd9  mov     rdi, [rbx+40h]
0x140019ddd  cmp     qword ptr [rdi+38h], 0
0x140019de2  jz      loc_140019ED1
0x140019de8  mov     rcx, [rbx+2A0h]
0x140019def  xor     edi, edi
0x140019df1  test    rcx, rcx
0x140019df4  jz      short loc_140019E18
0x140019df6  mov     eax, [rbp+8]
0x140019df9  bt      eax, 0Ah
0x140019dfd  jb      loc_140019F24
0x140019e03  bt      eax, 9
0x140019e07  jb      loc_140019FBB
0x140019e0d  mov     eax, [rcx+0Ch]
0x140019e10  test    al, 8
0x140019e12  jnz     loc_140019FC7
0x140019e18  call    cs:__imp_MRxSmbGetCompressionConfigBlock
0x140019e1f  nop     dword ptr [rax+rax+00h]
0x140019e24  test    byte ptr [rax+1Ah], 2
0x140019e28  jnz     short loc_140019E7F
0x140019e2a  call    cs:__imp_MRxSmbGetCompressionConfigBlock
0x140019e31  nop     dword ptr [rax+rax+00h]
0x140019e36  test    byte ptr [rax+1Ah], 1
0x140019e3a  jnz     loc_140019F03
0x140019e40  mov     ecx, [rbp+144h]
0x140019e46  cmp     ecx, 0FFFFFFFFh
0x140019e49  jz      short loc_140019E7F
0x140019e4b  mov     eax, [rsi+1DCh]
0x140019e51  cmp     eax, 0FFFFFFFFh
0x140019e54  jz      short loc_140019E7F
0x140019e56  cmp     eax, 1
0x140019e59  jz      loc_140019F14
0x140019e5f  cmp     ecx, 1
0x140019e62  jz      loc_140019F14
0x140019e68  mov     rcx, [rsi+1A8h]
0x140019e6f  test    dword ptr [rcx+0B4h], 80000h
0x140019e79  jnz     loc_140019F14
0x140019e7f  mov     eax, edi
0x140019e81  add     rsp, 48h
0x140019e85  pop     r15
0x140019e87  pop     r14
0x140019e89  pop     rdi
0x140019e8a  pop     rsi
0x140019e8b  pop     rbp
0x140019e8c  pop     rbx
0x140019e8d  retn
0x140019e8f  mov     edi, 0C000009Ah
0x140019e94  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140019e9b  lea     r14, WPP_GLOBAL_Control
0x140019ea2  cmp     rcx, r14
0x140019ea5  jz      short loc_140019E7F
0x140019ea7  mov     eax, [rcx+2Ch]
0x140019eaa  test    al, 1
0x140019eac  jz      short loc_140019E7F
0x140019eae  cmp     byte ptr [rcx+29h], 1
0x140019eb2  jb      short loc_140019E7F
0x140019eb4  mov     rcx, [rcx+18h]
0x140019eb8  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x140019ebf  mov     edx, 2Dh ; '-'
0x140019ec4  mov     r9d, 0C000009Ah
0x140019eca  call    WPP_SF_d
0x140019ecf  jmp     short loc_140019E7F
0x140019ed1  mov     edx, 38h ; '8'
0x140019ed6  mov     ecx, 100h
0x140019edb  mov     r8d, 6D536946h
0x140019ee1  call    cs:__imp_ExAllocatePool2
0x140019ee8  nop     dword ptr [rax+rax+00h]
0x140019eed  test    rax, rax
0x140019ef0  jz      short loc_140019F6B
0x140019ef2  mov     ecx, 0E420h
0x140019ef7  mov     [rax], cx
0x140019efa  mov     [rdi+38h], rax
0x140019efe  jmp     loc_140019DE8
0x140019f03  mov     rax, [rsi+18h]
0x140019f07  cmp     [rax+520h], dil
0x140019f0e  jnz     loc_140019E40
0x140019f14  mov     rcx, [rbx+40h]
0x140019f18  xor     edx, edx
0x140019f1a  call    Smb2EnableCompressionForFobx
0x140019f1f  jmp     loc_140019E7F
0x140019f24  mov     dword ptr [rcx+14h], 3
0x140019f2b  jmp     loc_140019E0D
0x140019f30  cmp     byte ptr [r10+29h], 2
0x140019f35  jb      loc_140019DCE
0x140019f3b  mov     rax, [rdi+50h]
0x140019f3f  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x140019f46  mov     [rsp+78h+var_48], rax
0x140019f4b  mov     edx, 2Eh ; '.'
0x140019f50  mov     [rsp+78h+var_50], rcx
0x140019f55  mov     r9, r15
0x140019f58  mov     rcx, [r10+18h]
0x140019f5c  mov     [rsp+78h+var_58], rdi
0x140019f61  call    WPP_SF_qqqZ
0x140019f66  jmp     loc_140019DCE
0x140019f6b  mov     edi, 0C000009Ah
0x140019f70  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140019f77  cmp     rcx, r14
0x140019f7a  jz      loc_140019E7F
0x140019f80  mov     eax, [rcx+2Ch]
0x140019f83  test    al, 1
0x140019f85  jz      loc_140019E7F
0x140019f8b  cmp     byte ptr [rcx+29h], 1
0x140019f8f  jb      loc_140019E7F
0x140019f95  mov     r9, [rbx+40h]
0x140019f99  lea     r8, WPP_584f9b0e749e3be8080bab44300b7711_Traceguids
0x140019fa0  mov     rcx, [rcx+18h]
0x140019fa4  mov     edx, 2Fh ; '/'
0x140019fa9  mov     dword ptr [rsp+78h+var_58], 0C000009Ah
0x140019fb1  call    WPP_SF_qD
0x140019fb6  jmp     loc_140019E7F
0x140019fbb  mov     dword ptr [rcx+14h], 2
0x140019fc2  jmp     loc_140019E0D
0x140019fc7  or      dword ptr [rcx+18h], 8
0x140019fcb  jmp     loc_140019E18
```
