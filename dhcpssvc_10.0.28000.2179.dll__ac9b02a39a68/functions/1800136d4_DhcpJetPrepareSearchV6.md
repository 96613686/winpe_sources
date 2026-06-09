# DhcpJetPrepareSearchV6

- ea: `0x1800136d4`
- end: `0x180013804`
- name: `DhcpJetPrepareSearchV6`
- size: `304`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180002b8c`
- `0x180011ea8`
- `0x180014490`
- `0x1800422a0`

## callees

- `0x18000282c`
- `0x18000e814`
- `0x1800136d4`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x180013707`
- `ESENT!JetSetCurrentIndex` at `0x180013707`
- `ESENT!JetMakeKey` at `0x1800137bd`
- `ESENT!JetMakeKey` at `0x1800137bd`
- `ESENT!JetSeek` at `0x1800137ec`
- `ESENT!JetSeek` at `0x1800137ec`
- `ESENT!JetMove` at `0x18001373c`
- `ESENT!JetMove` at `0x18001373c`

## string_xrefs

- `0x180013748`: `DhcpJetPrepareSearchV6:JetMove`

## pseudocode

```c
__int64 __fastcall DhcpJetPrepareSearchV6(
        __int64 a1,
        int a2,
        const void *a3,
        unsigned int a4,
        __int64 a5,
        JET_SESID sesid)
{
  JET_TABLEID v6; // rdi
  unsigned int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  const char *v13; // rdx
  unsigned int Key; // eax

  v6 = DhcpGlobalClientTableV6Handle;
  v10 = JetSetCurrentIndex(sesid, DhcpGlobalClientTableV6Handle, a1);
  v11 = DhcpMapJetError(v10, "DhcpJetPrepareSearchV6:JetSetCurrentIndex");
  if ( !v11 )
  {
    if ( a2 )
    {
      v12 = JetMove(sesid, v6, 0x80000000, 0);
      v13 = "DhcpJetPrepareSearchV6:JetMove";
      goto LABEL_4;
    }
    Key = JetMakeKey(sesid, v6, a3, a4, 1u);
    v11 = DhcpMapJetError(Key, "DhcpJetPrepareSearchV6:JetMakeKey");
    if ( !v11 )
    {
      v12 = JetSeek(sesid, v6, 1u);
      v13 = "DhcpJetPrepareSearchV6:JetSeek";
LABEL_4:
      v11 = DhcpMapJetError(v12, v13);
      if ( !v11 )
        return v11;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_41653652a8cc332f218bba10df165c1f_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x1800136d4  mov     rax, rsp
0x1800136d7  mov     [rax+8], rbx
0x1800136db  mov     [rax+10h], rbp
0x1800136df  mov     [rax+18h], rdi
0x1800136e3  mov     [rax+20h], r14
0x1800136e7  push    r15
0x1800136e9  sub     rsp, 30h
0x1800136ed  mov     rdi, cs:DhcpGlobalClientTableV6Handle
0x1800136f4  mov     r15, r8
0x1800136f7  mov     r8, rcx
0x1800136fa  mov     ebp, edx
0x1800136fc  mov     rcx, [rsp+38h+sesid]
0x180013701  mov     rdx, rdi
0x180013704  mov     r14d, r9d
0x180013707  call    cs:__imp_JetSetCurrentIndex
0x18001370e  nop     dword ptr [rax+rax+00h]
0x180013713  mov     ecx, eax
0x180013715  lea     rdx, aDhcpjetprepare_3; "DhcpJetPrepareSearchV6:JetSetCurrentInd"...
0x18001371c  call    DhcpMapJetError
0x180013721  mov     ebx, eax
0x180013723  test    eax, eax
0x180013725  jnz     short loc_18001375C
0x180013727  mov     rcx, [rsp+38h+sesid]; sesid
0x18001372c  mov     rdx, rdi; tableid
0x18001372f  test    ebp, ebp
0x180013731  jz      short loc_1800137AE
0x180013733  xor     r9d, r9d; grbit
0x180013736  mov     r8d, 80000000h; cRow
0x18001373c  call    cs:__imp_JetMove
0x180013743  nop     dword ptr [rax+rax+00h]
0x180013748  lea     rdx, aDhcpjetprepare_4; "DhcpJetPrepareSearchV6:JetMove"
0x18001374f  mov     ecx, eax
0x180013751  call    DhcpMapJetError
0x180013756  mov     ebx, eax
0x180013758  test    eax, eax
0x18001375a  jz      short loc_180013790
0x18001375c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013763  lea     rax, WPP_GLOBAL_Control
0x18001376a  cmp     rcx, rax
0x18001376d  jz      short loc_180013790
0x18001376f  test    dword ptr [rcx+1Ch], 800h
0x180013776  jz      short loc_180013790
0x180013778  mov     rcx, [rcx+10h]
0x18001377c  lea     r8, WPP_41653652a8cc332f218bba10df165c1f_Traceguids
0x180013783  mov     edx, 16h
0x180013788  mov     r9d, ebx
0x18001378b  call    WPP_SF_D
0x180013790  mov     rbp, [rsp+38h+arg_8]
0x180013795  mov     eax, ebx
0x180013797  mov     rbx, [rsp+38h+arg_0]
0x18001379c  mov     rdi, [rsp+38h+arg_10]
0x1800137a1  mov     r14, [rsp+38h+arg_18]
0x1800137a6  add     rsp, 30h
0x1800137aa  pop     r15
0x1800137ac  retn
0x1800137ae  mov     ebp, 1
0x1800137b3  mov     r9d, r14d; cbData
0x1800137b6  mov     r8, r15; pvData
0x1800137b9  mov     [rsp+38h+grbit], ebp; grbit
0x1800137bd  call    cs:__imp_JetMakeKey
0x1800137c4  nop     dword ptr [rax+rax+00h]
0x1800137c9  mov     ecx, eax
0x1800137cb  lea     rdx, aDhcpjetprepare_6; "DhcpJetPrepareSearchV6:JetMakeKey"
0x1800137d2  call    DhcpMapJetError
0x1800137d7  mov     ebx, eax
0x1800137d9  test    eax, eax
0x1800137db  jnz     loc_18001375C
0x1800137e1  mov     rcx, [rsp+38h+sesid]; sesid
0x1800137e6  mov     r8d, ebp; grbit
0x1800137e9  mov     rdx, rdi; tableid
0x1800137ec  call    cs:__imp_JetSeek
0x1800137f3  nop     dword ptr [rax+rax+00h]
0x1800137f8  lea     rdx, aDhcpjetprepare_9; "DhcpJetPrepareSearchV6:JetSeek"
0x1800137ff  jmp     loc_18001374F
```
