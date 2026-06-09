# CILogWrite::SetCheckpoint(_ULARGE_INTEGER)

- ea: `0x180004ff0`
- end: `0x1800051ef`
- name: `?SetCheckpoint@CILogWrite@@UEAAJT_ULARGE_INTEGER@@@Z`
- size: `511`
- prototype: `__int64 __fastcall(CILogWrite *__hidden this, union _ULARGE_INTEGER)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180004708`
- `0x180004ff0`
- `0x180008090`
- `0x18000d998`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800051a8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800051a8`

## string_xrefs

- `0x1800050b3`: `com\complus\dtc\dtc\log\logmgr\src\ilgwrite.cpp`

## pseudocode

```c
__int64 __fastcall CILogWrite::SetCheckpoint(CILogWrite *this, union _ULARGE_INTEGER a2)
{
  __int64 v4; // r9
  __int64 v5; // rcx
  int v6; // eax
  unsigned int v7; // edi
  unsigned int v9; // r15d
  struct _STRMTBL *Stream; // rdi
  __int64 v11; // r14
  __int64 v12; // rax
  union _ULARGE_INTEGER *v13; // rdx
  union _ULARGE_INTEGER v14; // rdx

  if ( !a2.QuadPart )
    return 2147942487LL;
  v4 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v4 + 620) - a2.HighPart > 1
    || a2.HighPart > *(_DWORD *)(v4 + 620)
    || (*(unsigned int (__fastcall **)(__int64, _QWORD, union _ULARGE_INTEGER))(*(_QWORD *)(v4 + 144) + 24LL))(
         v4 + 144,
         *(_QWORD *)(v4 + 616),
         a2) == 1 )
  {
    return 2147942487LL;
  }
  v5 = *(_QWORD *)(*((_QWORD *)this + 2) + 24LL);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, int, _DWORD, _QWORD, _QWORD))(*(_QWORD *)v5 + 24LL))(
           v5,
           256,
           4,
           0,
           1073745966,
           0,
           0,
           0);
    v7 = v6;
    if ( v6 < 0 )
    {
      TraceFile(
        v6,
        "failed in m_pCLogMgr->m_pIDtcTrace->Trace",
        "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\ilgwrite.cpp",
        0x137u);
      return v7;
    }
  }
  v9 = 0;
  Stream = CILogStorage::GetStream(
             (CILogStorage *)(*((_QWORD *)this + 2) + 96LL),
             *(_DWORD *)(*((_QWORD *)this + 1) + 328LL));
  if ( !Stream )
    return 2147549183LL;
  v11 = *((_QWORD *)this + 2) + 304LL;
  (**(void (__fastcall ***)(__int64))v11)(v11);
  *(union _ULARGE_INTEGER *)((char *)Stream + 8 * (unsigned __int16)(*((_WORD *)Stream + 9))++ + 28) = a2;
  v12 = *((unsigned __int16 *)Stream + 9);
  if ( (_WORD)v12 == 2 )
  {
    LOWORD(v12) = 0;
    *((_WORD *)Stream + 9) = 0;
  }
  else if ( (unsigned __int16)v12 >= 2u )
  {
    v13 = (union _ULARGE_INTEGER *)((char *)Stream + 8 * v12 + 12);
    goto LABEL_14;
  }
  v13 = (union _ULARGE_INTEGER *)((char *)Stream + 8 * (unsigned __int16)v12 + 28);
LABEL_14:
  v14 = *v13;
  if ( v14.QuadPart
    && (*(union _ULARGE_INTEGER *)(*(_QWORD *)((char *)Stream + 20) + 592LL) = v14,
        (v9 = CLogMgr::_SetLowWater(*((CLogMgr **)this + 2), v14, 1)) != 0) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    return v9;
  }
  else
  {
    _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 2) + 388LL), 1u);
    SetEvent(*(HANDLE *)(*((_QWORD *)this + 2) + 552LL));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    return v9;
  }
}

```

## disassembly

```asm
0x180004ff0  push    rbx
0x180004ff2  push    rsi
0x180004ff3  push    rdi
0x180004ff4  push    r13
0x180004ff6  push    r14
0x180004ff8  push    r15
0x180004ffa  sub     rsp, 78h
0x180004ffe  mov     rbx, rdx
0x180005001  mov     rsi, rcx
0x180005004  test    rdx, rdx
0x180005007  jz      loc_1800051DB
0x18000500d  mov     r9, [rcx+10h]
0x180005011  mov     edx, [r9+26Ch]
0x180005018  mov     rcx, rbx
0x18000501b  shr     rcx, 20h
0x18000501f  mov     eax, edx
0x180005021  sub     eax, ecx
0x180005023  mov     r13d, 1
0x180005029  cmp     eax, r13d
0x18000502c  ja      loc_1800051DB
0x180005032  cmp     ecx, edx
0x180005034  ja      loc_1800051DB
0x18000503a  lea     rcx, [r9+90h]
0x180005041  mov     rax, [rcx]
0x180005044  mov     r8, rbx
0x180005047  mov     rdx, [r9+268h]
0x18000504e  mov     rax, [rax+18h]
0x180005052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005057  cmp     eax, r13d
0x18000505a  jz      loc_1800051DB
0x180005060  mov     rax, [rsi+10h]
0x180005064  mov     rcx, [rax+18h]
0x180005068  test    rcx, rcx
0x18000506b  jz      short loc_1800050CF
0x18000506d  mov     rax, [rcx]
0x180005070  mov     [rsp+0A8h+var_70], 0
0x180005079  mov     [rsp+0A8h+var_78], 0
0x180005082  mov     [rsp+0A8h+var_80], 0
0x18000508a  mov     [rsp+0A8h+var_88], 4000102Eh
0x180005092  xor     r9d, r9d
0x180005095  mov     edx, 100h
0x18000509a  lea     r8d, [r13+3]
0x18000509e  mov     rax, [rax+18h]
0x1800050a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050a7  mov     edi, eax
0x1800050a9  test    eax, eax
0x1800050ab  jns     short loc_1800050CF
0x1800050ad  mov     r9d, 137h; unsigned int
0x1800050b3  lea     r8, aComComplusDtcD_1; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x1800050ba  lea     rdx, aFailedInMPclog; "failed in m_pCLogMgr->m_pIDtcTrace->Tra"...
0x1800050c1  mov     ecx, eax; int
0x1800050c3  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x1800050c8  mov     eax, edi
0x1800050ca  jmp     loc_1800051E0
0x1800050cf  xor     r15d, r15d
0x1800050d2  mov     rdx, [rsi+8]
0x1800050d6  mov     rcx, [rsi+10h]
0x1800050da  add     rcx, 60h ; '`'; this
0x1800050de  mov     edx, [rdx+148h]; unsigned int
0x1800050e4  call    ?GetStream@CILogStorage@@AEAAPEAU_STRMTBL@@K@Z; CILogStorage::GetStream(ulong)
0x1800050e9  mov     rdi, rax
0x1800050ec  test    rax, rax
0x1800050ef  jz      loc_1800051D4
0x1800050f5  mov     r14, [rsi+10h]
0x1800050f9  add     r14, 130h
0x180005100  mov     [rsp+0A8h+var_50], r13d
0x180005105  mov     [rsp+0A8h+var_48], r14
0x18000510a  mov     rcx, [r14]
0x18000510d  mov     rax, [rcx]
0x180005110  mov     rcx, r14
0x180005113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005118  nop
0x180005119  movzx   eax, word ptr [rdi+12h]
0x18000511d  mov     [rdi+rax*8+1Ch], rbx
0x180005122  add     [rdi+12h], r13w
0x180005127  movzx   eax, word ptr [rdi+12h]
0x18000512b  lea     ecx, [r15+2]
0x18000512f  cmp     ax, cx
0x180005132  jnz     short loc_18000513C
0x180005134  xor     eax, eax
0x180005136  mov     [rdi+12h], ax
0x18000513a  jmp     short loc_18000513E
0x18000513c  jnb     short loc_18000514B
0x18000513e  movzx   eax, ax
0x180005141  lea     rdx, [rdi+1Ch]
0x180005145  lea     rdx, [rdx+rax*8]
0x180005149  jmp     short loc_180005156
0x18000514b  lea     rdx, ds:0Ch[rax*8]
0x180005153  add     rdx, rdi
0x180005156  mov     rdx, [rdx]; union _ULARGE_INTEGER
0x180005159  test    rdx, rdx
0x18000515c  jz      short loc_180005191
0x18000515e  mov     rax, [rdi+14h]
0x180005162  mov     [rax+250h], rdx
0x180005169  mov     r8d, r13d; int
0x18000516c  mov     rcx, [rsi+10h]; this
0x180005170  call    ?_SetLowWater@CLogMgr@@QEAAJT_ULARGE_INTEGER@@H@Z; CLogMgr::_SetLowWater(_ULARGE_INTEGER,int)
0x180005175  mov     r15d, eax
0x180005178  test    eax, eax
0x18000517a  jz      short loc_180005191
0x18000517c  mov     rax, [r14]
0x18000517f  mov     rcx, r14
0x180005182  mov     rax, [rax+8]
0x180005186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000518b  nop
0x18000518c  mov     eax, r15d
0x18000518f  jmp     short loc_1800051E0
0x180005191  mov     rax, [rsi+10h]
0x180005195  lock add [rax+184h], r13d
0x18000519d  mov     rcx, [rsi+10h]
0x1800051a1  mov     rcx, [rcx+228h]; hEvent
0x1800051a8  call    cs:__imp_SetEvent
0x1800051ae  nop
0x1800051af  mov     rax, [r14]
0x1800051b2  mov     rcx, r14
0x1800051b5  mov     rax, [rax+8]
0x1800051b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051be  nop
0x1800051bf  jmp     short loc_1800051CF
0x1800051c1  mov     eax, [rsp+0A8h+var_58]
0x1800051c5  jmp     short loc_1800051E0
0x1800051c7  mov     r15d, [rsp+0A8h+arg_8]
0x1800051cf  mov     eax, r15d
0x1800051d2  jmp     short loc_1800051E0
0x1800051d4  mov     eax, 8000FFFFh
0x1800051d9  jmp     short loc_1800051E0
0x1800051db  mov     eax, 80070057h
0x1800051e0  add     rsp, 78h
0x1800051e4  pop     r15
0x1800051e6  pop     r14
0x1800051e8  pop     r13
0x1800051ea  pop     rdi
0x1800051eb  pop     rsi
0x1800051ec  pop     rbx
0x1800051ed  retn
```
