# CRdpHintManager::OnWindowCreated(IRdpWindowTracker *,unsigned __int64)

- ea: `0x140034e40`
- end: `0x140035119`
- name: `?OnWindowCreated@CRdpHintManager@@UEAAJPEAVIRdpWindowTracker@@_K@Z`
- size: `729`
- prototype: `int(CRdpHintManager *__hidden this, struct IRdpWindowTracker *, unsigned __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x140004cf4`
- `0x140005750`
- `0x14000d350`
- `0x14000efb8`
- `0x1400188b0`
- `0x14001c620`
- `0x1400333cc`
- `0x140034e40`
- `0x14003743c`
- `0x14006a120`
- `0x14006b010`

## import_xrefs

- `USER32!GetClassNameW` at `0x140034ea3`
- `USER32!GetClassNameW` at `0x140034ea3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140034f5b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140034f5b`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x140034fe5`
- `api-ms-win-security-systemfunctions-l1-1-0!SystemFunction036` at `0x140034fe5`

## string_xrefs

- `0x140035047`: `CreateHintNode failed`

## pseudocode

```c
__int64 __fastcall CRdpHintManager::OnWindowCreated(void **this, struct IRdpWindowTracker *a2, HWND a3)
{
  CVPtrList *v6; // rcx
  int v7; // edi
  unsigned int v8; // eax
  int v9; // edx
  const char *v10; // rcx
  void *v11; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v13; // edx
  int v14; // r8d
  int HintNode; // edi
  unsigned int v16; // eax
  int cchCount2[2]; // [rsp+28h] [rbp-D8h]
  int cchCount1[2]; // [rsp+30h] [rbp-D0h] BYREF
  void *v20; // [rsp+38h] [rbp-C8h] BYREF
  void *v21[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ClassName[128]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(ClassName, 0, sizeof(ClassName));
  *(_QWORD *)cchCount1 = 0;
  v20 = 0;
  GetClassNameW(a3, ClassName, 128);
  v7 = StringCchLengthW(ClassName, 0x80u, (unsigned __int64 *)cchCount1);
  if ( v7 >= 0 )
  {
    v21[0] = this[64];
    while ( (unsigned int)CVPtrList::GetNext(v6, v21, &v20) )
    {
      v11 = v20;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v20 + 4) + 8LL))(*((_QWORD *)v20 + 4));
      if ( CompareStringW(0x7Fu, 1u, ClassName, cchCount1[0], *((PCNZWCH *)v11 + 7), *((_DWORD *)v11 + 12)) == 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DqS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v13,
            v14,
            CurrentThreadActivityIdPrefix,
            (char)a3,
            (__int64)ClassName);
        }
        *(_QWORD *)cchCount1 = 0;
        v21[0] = this + 1;
        CTSCriticalSection::Lock((CTSCriticalSection *)(this + 1));
        SystemFunction036(cchCount1, 8u);
        *(_QWORD *)cchCount1 = (unsigned __int64)a3 | (*(_QWORD *)cchCount1 << 32) | 0x8000000000000000uLL;
        HintNode = CRdpHintManager::CreateHintNode((CRdpHintManager *)(this - 6), *(__int64 *)cchCount1, 1, a3, 0);
        if ( HintNode < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = RdpWppGetCurrentThreadActivityIdPrefix();
          cchCount2[0] = HintNode;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
            v16,
            (__int64)"CreateHintNode failed",
            *(_QWORD *)cchCount2);
        }
        CTSAutoLock::~CTSAutoLock((CTSAutoLock *)v21);
        v7 = (*(__int64 (__fastcall **)(struct IRdpWindowTracker *, HWND, __int64))(*(_QWORD *)a2 + 24LL))(a2, a3, 1);
        if ( v7 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = RdpWppGetCurrentThreadActivityIdPrefix();
          v9 = 42;
          v10 = "pSender->TrackWindow() failed";
          goto LABEL_24;
        }
        break;
      }
      TCntPtr<CRdpClipMainWnd>::SafeRelease(&v20);
      v20 = 0;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 39;
    v10 = "StringCchLength() failed";
LABEL_24:
    cchCount2[0] = v7;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
      v8,
      (__int64)v10,
      *(_QWORD *)cchCount2);
  }
  TCntPtr<CRdpClipMainWnd>::SafeRelease(&v20);
  return 0;
}

```

## disassembly

```asm
0x140034e40  mov     [rsp-8+arg_18], rbx
0x140034e45  push    rbp
0x140034e46  push    rsi
0x140034e47  push    rdi
0x140034e48  push    r14
0x140034e4a  push    r15
0x140034e4c  lea     rbp, [rsp-60h]
0x140034e51  sub     rsp, 160h
0x140034e58  mov     rax, cs:__security_cookie
0x140034e5f  xor     rax, rsp
0x140034e62  mov     [rbp+80h+var_30], rax
0x140034e66  mov     rsi, r8
0x140034e69  mov     r15, rdx
0x140034e6c  mov     r14, rcx
0x140034e6f  xor     edx, edx; Val
0x140034e71  mov     r8d, 100h; Size
0x140034e77  lea     rcx, [rsp+180h+ClassName]; void *
0x140034e7c  call    memset_0
0x140034e81  mov     ebx, 80h
0x140034e86  mov     qword ptr [rsp+180h+cchCount1], 0
0x140034e8f  mov     r8d, ebx; nMaxCount
0x140034e92  mov     [rsp+180h+var_148], 0
0x140034e9b  lea     rdx, [rsp+180h+ClassName]; lpClassName
0x140034ea0  mov     rcx, rsi; hWnd
0x140034ea3  call    cs:__imp_GetClassNameW
0x140034ea9  lea     r8, [rsp+180h+cchCount1]; unsigned __int64 *
0x140034eae  mov     edx, ebx; unsigned __int64
0x140034eb0  lea     rcx, [rsp+180h+ClassName]; unsigned __int16 *
0x140034eb5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140034eba  mov     edi, eax
0x140034ebc  test    eax, eax
0x140034ebe  jns     short loc_140034F01
0x140034ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x140034ec7  lea     rbx, WPP_GLOBAL_Control
0x140034ece  cmp     rcx, rbx
0x140034ed1  jz      loc_1400350EA
0x140034ed7  test    byte ptr [rcx+1Ch], 8
0x140034edb  jz      loc_1400350EA
0x140034ee1  cmp     byte ptr [rcx+19h], 2
0x140034ee5  jb      loc_1400350EA
0x140034eeb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140034ef0  mov     edx, 27h ; '''
0x140034ef5  lea     rcx, aStringcchlengt_1; "StringCchLength() failed"
0x140034efc  jmp     loc_1400350C7
0x140034f01  mov     rax, [r14+200h]
0x140034f08  mov     [rsp+180h+var_140], rax
0x140034f0d  lea     r8, [rsp+180h+var_148]; void **
0x140034f12  lea     rdx, [rsp+180h+var_140]; void **
0x140034f17  call    ?GetNext@CVPtrList@@QEBAHAEAPEAXPEAPEAX@Z; CVPtrList::GetNext(void * &,void * *)
0x140034f1c  test    eax, eax
0x140034f1e  jz      loc_1400350EA
0x140034f24  mov     rbx, [rsp+180h+var_148]
0x140034f29  mov     rcx, [rbx+20h]
0x140034f2d  mov     rax, [rcx]
0x140034f30  mov     rax, [rax+8]
0x140034f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034f39  mov     eax, [rbx+30h]
0x140034f3c  lea     r8, [rsp+180h+ClassName]; lpString1
0x140034f41  mov     r9d, [rsp+180h+cchCount1]; cchCount1
0x140034f46  mov     edx, 1; dwCmpFlags
0x140034f4b  mov     [rsp+180h+cchCount2], eax; cchCount2
0x140034f4f  mov     rax, [rbx+38h]
0x140034f53  mov     [rsp+180h+lpString2], rax; lpString2
0x140034f58  lea     ecx, [rdx+7Eh]; Locale
0x140034f5b  call    cs:__imp_CompareStringW
0x140034f61  cmp     eax, 2
0x140034f64  jz      short loc_140034F7B
0x140034f66  lea     rcx, [rsp+180h+var_148]
0x140034f6b  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x140034f70  mov     [rsp+180h+var_148], 0
0x140034f79  jmp     short loc_140034F0D
0x140034f7b  mov     rax, cs:WPP_GLOBAL_Control
0x140034f82  lea     rbx, WPP_GLOBAL_Control
0x140034f89  cmp     rax, rbx
0x140034f8c  jz      short loc_140034FC4
0x140034f8e  test    dword ptr [rax+1Ch], 200h
0x140034f95  jz      short loc_140034FC4
0x140034f97  cmp     byte ptr [rax+19h], 4
0x140034f9b  jb      short loc_140034FC4
0x140034f9d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140034fa2  lea     rcx, [rsp+180h+ClassName]
0x140034fa7  mov     r9d, eax
0x140034faa  mov     qword ptr [rsp+180h+cchCount2], rcx
0x140034faf  mov     rcx, cs:WPP_GLOBAL_Control
0x140034fb6  mov     [rsp+180h+lpString2], rsi
0x140034fbb  mov     rcx, [rcx+10h]
0x140034fbf  call    WPP_SF_DqS
0x140034fc4  lea     rcx, [r14+8]; this
0x140034fc8  mov     qword ptr [rsp+180h+cchCount1], 0
0x140034fd1  mov     [rsp+180h+var_140], rcx
0x140034fd6  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x140034fdb  mov     edx, 8; RandomBufferLength
0x140034fe0  lea     rcx, [rsp+180h+cchCount1]; RandomBuffer
0x140034fe5  call    cs:__imp_SystemFunction036
0x140034feb  mov     rdx, qword ptr [rsp+180h+cchCount1]
0x140034ff0  lea     rcx, [r14-30h]; this
0x140034ff4  shl     rdx, 20h
0x140034ff8  mov     rax, 8000000000000000h
0x140035002  or      rdx, rsi
0x140035005  mov     [rsp+180h+lpString2], 0; struct tagRECT *
0x14003500e  or      rdx, rax; unsigned __int64
0x140035011  mov     r9, rsi; HWND
0x140035014  mov     r8d, 1; unsigned int
0x14003501a  mov     qword ptr [rsp+180h+cchCount1], rdx
0x14003501f  call    ?CreateHintNode@CRdpHintManager@@AEAAJ_KKPEAUHWND__@@PEAUtagRECT@@@Z; CRdpHintManager::CreateHintNode(unsigned __int64,ulong,HWND__ *,tagRECT *)
0x140035024  mov     edi, eax
0x140035026  test    eax, eax
0x140035028  jns     short loc_140035076
0x14003502a  mov     rcx, cs:WPP_GLOBAL_Control
0x140035031  cmp     rcx, rbx
0x140035034  jz      short loc_140035076
0x140035036  test    byte ptr [rcx+1Ch], 8
0x14003503a  jz      short loc_140035076
0x14003503c  cmp     byte ptr [rcx+19h], 2
0x140035040  jb      short loc_140035076
0x140035042  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140035047  lea     rcx, aCreatehintnode_0; "CreateHintNode failed"
0x14003504e  mov     [rsp+180h+cchCount2], edi
0x140035052  mov     [rsp+180h+lpString2], rcx
0x140035057  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x14003505e  mov     rcx, cs:WPP_GLOBAL_Control
0x140035065  mov     edx, 29h ; ')'
0x14003506a  mov     r9d, eax
0x14003506d  mov     rcx, [rcx+10h]
0x140035071  call    WPP_SF_DsD
0x140035076  lea     rcx, [rsp+180h+var_140]; this
0x14003507b  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x140035080  mov     rax, [r15]
0x140035083  mov     r8d, 1
0x140035089  mov     rdx, rsi
0x14003508c  mov     rcx, r15
0x14003508f  mov     rax, [rax+18h]
0x140035093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035098  mov     edi, eax
0x14003509a  test    eax, eax
0x14003509c  jns     short loc_1400350EA
0x14003509e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400350a5  cmp     rcx, rbx
0x1400350a8  jz      short loc_1400350EA
0x1400350aa  test    byte ptr [rcx+1Ch], 8
0x1400350ae  jz      short loc_1400350EA
0x1400350b0  cmp     byte ptr [rcx+19h], 2
0x1400350b4  jb      short loc_1400350EA
0x1400350b6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400350bb  mov     edx, 2Ah ; '*'
0x1400350c0  lea     rcx, aPsenderTrackwi; "pSender->TrackWindow() failed"
0x1400350c7  mov     [rsp+180h+cchCount2], edi
0x1400350cb  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x1400350d2  mov     [rsp+180h+lpString2], rcx
0x1400350d7  mov     r9d, eax
0x1400350da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400350e1  mov     rcx, [rcx+10h]
0x1400350e5  call    WPP_SF_DsD
0x1400350ea  lea     rcx, [rsp+180h+var_148]
0x1400350ef  call    ?SafeRelease@?$TCntPtr@VCRdpClipMainWnd@@@@AEAAXXZ; TCntPtr<CRdpClipMainWnd>::SafeRelease(void)
0x1400350f4  xor     eax, eax
0x1400350f6  mov     rcx, [rbp+80h+var_30]
0x1400350fa  xor     rcx, rsp; StackCookie
0x1400350fd  call    __security_check_cookie
0x140035102  mov     rbx, [rsp+180h+arg_18]
0x14003510a  add     rsp, 160h
0x140035111  pop     r15
0x140035113  pop     r14
0x140035115  pop     rdi
0x140035116  pop     rsi
0x140035117  pop     rbp
0x140035118  retn
```
