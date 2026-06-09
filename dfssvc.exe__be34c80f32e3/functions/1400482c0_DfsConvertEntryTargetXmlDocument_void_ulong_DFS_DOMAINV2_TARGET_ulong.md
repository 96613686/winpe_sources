# DfsConvertEntryTargetXmlDocument(void *,ulong,_DFS_DOMAINV2_TARGET * *,ulong *)

- ea: `0x1400482c0`
- end: `0x140048573`
- name: `?DfsConvertEntryTargetXmlDocument@@YAKPEAXKPEAPEAU_DFS_DOMAINV2_TARGET@@PEAK@Z`
- size: `691`
- prototype: `unsigned int __fastcall(void *, unsigned int, struct _DFS_DOMAINV2_TARGET **, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x1400413a8`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140005a94`
- `0x140005ad8`
- `0x1400482c0`
- `0x140048c30`
- `0x140048f24`
- `0x140049124`
- `0x1400496a8`
- `0x140058a38`
- `0x14005ce3a`
- `0x14005e010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x140048336`
- `XmlLite!CreateXmlReader` at `0x140048336`

## pseudocode

```c
__int64 __fastcall DfsConvertEntryTargetXmlDocument(
        void *a1,
        __int64 a2,
        struct _DFS_DOMAINV2_TARGET **a3,
        unsigned int *a4)
{
  struct _DFS_DOMAINV2_TARGET *v4; // rdi
  HRESULT MemoryStream; // eax
  unsigned int ErrorFromHr; // ebx
  _UNKNOWN **v9; // rax
  unsigned int v10; // r14d
  __int64 v11; // rsi
  unsigned int *v12; // rcx
  struct _DFS_DOMAINV2_TARGET *v13; // rax
  __int64 v14; // r14
  unsigned int TargetInfo; // eax
  unsigned int v17; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v18; // [rsp+34h] [rbp-1Ch] BYREF
  __int64 v19; // [rsp+38h] [rbp-18h] BYREF
  void *ppvObject; // [rsp+40h] [rbp-10h] BYREF
  char *v21; // [rsp+48h] [rbp-8h] BYREF

  v4 = 0;
  v21 = 0;
  v18 = 0;
  v17 = 0;
  ppvObject = 0;
  v19 = 0;
  MemoryStream = anonymous_namespace_::DfsMemoryStream::_CreateMemoryStream(a1, a2, (unsigned int)a2);
  if ( MemoryStream < 0
    || (MemoryStream = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0), MemoryStream < 0)
    || (MemoryStream = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvObject + 24LL))(ppvObject, 0),
        MemoryStream < 0) )
  {
    ErrorFromHr = DfsGetErrorFromHr(MemoryStream);
  }
  else
  {
    ErrorFromHr = anonymous_namespace_::DfspGetDocumentRootElementInfo(
                    (_DWORD)ppvObject,
                    (unsigned int)&v19 + 4,
                    (unsigned int)&v19,
                    (unsigned int)&v18,
                    (__int64)&v17);
    if ( !ErrorFromHr )
    {
      v9 = (_UNKNOWN **)WPP_GLOBAL_Control;
      v10 = v17;
      v11 = v18;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v12 = pWppControl;
        if ( pWppControl && (pWppControl[7] & 0x20) != 0 && *((_BYTE *)pWppControl + 25) >= 2u )
        {
          WPP_SF_dD(
            *((_QWORD *)pWppControl + 2),
            10,
            WPP_776a9413f9143c79b55c3fad11ed3a14_Traceguids,
            HIDWORD(v19),
            v19);
          v9 = (_UNKNOWN **)WPP_GLOBAL_Control;
          v12 = pWppControl;
        }
        if ( v9 != &WPP_GLOBAL_Control )
        {
          if ( v12 && (v12[7] & 0x20) != 0 && *((_BYTE *)v12 + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)v12 + 2), 11, WPP_776a9413f9143c79b55c3fad11ed3a14_Traceguids, (unsigned int)v11);
            v9 = (_UNKNOWN **)WPP_GLOBAL_Control;
            v12 = pWppControl;
          }
          if ( v9 != &WPP_GLOBAL_Control && v12 && (v12[7] & 0x20) != 0 && *((_BYTE *)v12 + 25) >= 2u )
            WPP_SF_D(*((_QWORD *)v12 + 2), 12, WPP_776a9413f9143c79b55c3fad11ed3a14_Traceguids, v10);
        }
      }
      v13 = (struct _DFS_DOMAINV2_TARGET *)operator new(v10 + 24 * (_DWORD)v11);
      v4 = v13;
      if ( v13 )
      {
        memset_0(v13, 0, v10 + 24 * (_DWORD)v11);
        HIDWORD(v19) = v10;
        v14 = 0;
        v21 = (char *)v4 + 24 * v11;
        while ( (unsigned int)v14 < (unsigned int)v11 )
        {
          TargetInfo = anonymous_namespace_::DfspGetTargetInfo(ppvObject, (char *)v4 + 24 * v14, &v21, (char *)&v19 + 4);
          v14 = (unsigned int)(v14 + 1);
          ErrorFromHr = TargetInfo;
          if ( TargetInfo )
            goto LABEL_30;
        }
        if ( (unsigned int)anonymous_namespace_::DfspLocateElement(ppvObject, L"target") == 1168 )
        {
          *a4 = v11;
          *a3 = v4;
          v4 = 0;
          ErrorFromHr = 0;
        }
        else
        {
          ErrorFromHr = -1073727281;
        }
      }
      else
      {
        ErrorFromHr = 8;
      }
    }
  }
LABEL_30:
  operator delete(v4);
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 13, WPP_776a9413f9143c79b55c3fad11ed3a14_Traceguids, ErrorFromHr);
  }
  return ErrorFromHr;
}

```

## disassembly

```asm
0x1400482c0  mov     r11, rsp
0x1400482c3  mov     [r11+8], rbx
0x1400482c7  mov     [r11+10h], rsi
0x1400482cb  mov     [r11+18h], rdi
0x1400482cf  push    rbp
0x1400482d0  push    r12
0x1400482d2  push    r13
0x1400482d4  push    r14
0x1400482d6  push    r15
0x1400482d8  mov     rbp, rsp
0x1400482db  sub     rsp, 50h
0x1400482df  xor     edi, edi
0x1400482e1  lea     rax, [rbp+var_8]
0x1400482e5  and     [rbp+var_8], rdi
0x1400482e9  mov     r13, r8
0x1400482ec  and     [rbp+ppvObject], rdi
0x1400482f0  mov     r8d, edx
0x1400482f3  and     [rbp+var_1C], edi
0x1400482f6  mov     r12, r9
0x1400482f9  and     [rbp+var_20], edi
0x1400482fc  and     dword ptr [rbp+var_18+4], edi
0x1400482ff  and     dword ptr [rbp+var_18], edi
0x140048302  mov     [r11-58h], rax
0x140048306  call    _anonymous_namespace___DfsMemoryStream___CreateMemoryStream
0x14004830b  mov     r15, [rbp+var_8]
0x14004830f  lea     rsi, WPP_GLOBAL_Control
0x140048316  test    eax, eax
0x140048318  jns     short loc_140048328
0x14004831a  mov     ecx, eax; int
0x14004831c  call    ?DfsGetErrorFromHr@@YAKJ@Z; DfsGetErrorFromHr(long)
0x140048321  mov     ebx, eax
0x140048323  jmp     loc_1400484E8
0x140048328  xor     r8d, r8d; pMalloc
0x14004832b  lea     rdx, [rbp+ppvObject]; ppvObject
0x14004832f  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x140048336  call    cs:__imp_CreateXmlReader
0x14004833d  nop     dword ptr [rax+rax+00h]
0x140048342  test    eax, eax
0x140048344  js      short loc_14004831A
0x140048346  mov     rcx, [rbp+ppvObject]
0x14004834a  mov     rdx, r15
0x14004834d  mov     rax, [rcx]
0x140048350  mov     rax, [rax+18h]
0x140048354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048359  test    eax, eax
0x14004835b  js      short loc_14004831A
0x14004835d  mov     rcx, [rbp+ppvObject]
0x140048361  lea     rax, [rbp+var_20]
0x140048365  lea     r9, [rbp+var_1C]
0x140048369  mov     [rsp+50h+var_30], rax
0x14004836e  lea     r8, [rbp+var_18]
0x140048372  lea     rdx, [rbp+var_18+4]
0x140048376  call    _anonymous_namespace___DfspGetDocumentRootElementInfo
0x14004837b  mov     ebx, eax
0x14004837d  test    eax, eax
0x14004837f  jnz     loc_1400484E8
0x140048385  mov     rax, cs:WPP_GLOBAL_Control
0x14004838c  lea     rbx, WPP_GLOBAL_Control
0x140048393  mov     r14d, [rbp+var_20]
0x140048397  mov     esi, [rbp+var_1C]
0x14004839a  cmp     rax, rbx
0x14004839d  jz      loc_140048453
0x1400483a3  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400483aa  test    rcx, rcx
0x1400483ad  jz      short loc_1400483E9
0x1400483af  test    byte ptr [rcx+1Ch], 20h
0x1400483b3  jz      short loc_1400483E9
0x1400483b5  cmp     byte ptr [rcx+19h], 2
0x1400483b9  jb      short loc_1400483E9
0x1400483bb  mov     eax, dword ptr [rbp+var_18]
0x1400483be  lea     r8, WPP_776a9413f9143c79b55c3fad11ed3a14_Traceguids
0x1400483c5  mov     r9d, dword ptr [rbp+var_18+4]
0x1400483c9  mov     edx, 0Ah
0x1400483ce  mov     rcx, [rcx+10h]
0x1400483d2  mov     dword ptr [rsp+50h+var_30], eax
0x1400483d6  call    WPP_SF_dD
0x1400483db  mov     rax, cs:WPP_GLOBAL_Control
0x1400483e2  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400483e9  cmp     rax, rbx
0x1400483ec  jz      short loc_140048453
0x1400483ee  test    rcx, rcx
0x1400483f1  jz      short loc_140048425
0x1400483f3  test    byte ptr [rcx+1Ch], 20h
0x1400483f7  jz      short loc_140048425
0x1400483f9  cmp     byte ptr [rcx+19h], 2
0x1400483fd  jb      short loc_140048425
0x1400483ff  mov     rcx, [rcx+10h]
0x140048403  lea     r8, WPP_776a9413f9143c79b55c3fad11ed3a14_Traceguids
0x14004840a  mov     edx, 0Bh
0x14004840f  mov     r9d, esi
0x140048412  call    WPP_SF_D
0x140048417  mov     rax, cs:WPP_GLOBAL_Control
0x14004841e  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140048425  cmp     rax, rbx
0x140048428  jz      short loc_140048453
0x14004842a  test    rcx, rcx
0x14004842d  jz      short loc_140048453
0x14004842f  test    byte ptr [rcx+1Ch], 20h
0x140048433  jz      short loc_140048453
0x140048435  cmp     byte ptr [rcx+19h], 2
0x140048439  jb      short loc_140048453
0x14004843b  mov     rcx, [rcx+10h]
0x14004843f  lea     r8, WPP_776a9413f9143c79b55c3fad11ed3a14_Traceguids
0x140048446  mov     edx, 0Ch
0x14004844b  mov     r9d, r14d
0x14004844e  call    WPP_SF_D
0x140048453  lea     eax, [rsi+rsi*2]
0x140048456  lea     ecx, [r14+rax*8]; Size
0x14004845a  mov     ebx, ecx
0x14004845c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140048461  mov     rdi, rax
0x140048464  test    rax, rax
0x140048467  jnz     short loc_14004846E
0x140048469  lea     ebx, [rax+8]
0x14004846c  jmp     short loc_1400484E1
0x14004846e  mov     r8, rbx; Size
0x140048471  xor     edx, edx; Val
0x140048473  mov     rcx, rdi; void *
0x140048476  call    memset_0
0x14004847b  lea     rcx, [rsi+rsi*2]
0x14004847f  mov     dword ptr [rbp+var_18+4], r14d
0x140048483  lea     rax, [rdi+rcx*8]
0x140048487  xor     r14d, r14d
0x14004848a  mov     [rbp+var_8], rax
0x14004848e  cmp     r14d, esi
0x140048491  jnb     short loc_1400484B7
0x140048493  lea     rcx, [r14+r14*2]
0x140048497  lea     rdx, [rdi+rcx*8]
0x14004849b  mov     rcx, [rbp+ppvObject]
0x14004849f  lea     r9, [rbp+var_18+4]
0x1400484a3  lea     r8, [rbp+var_8]
0x1400484a7  call    _anonymous_namespace___DfspGetTargetInfo
0x1400484ac  inc     r14d
0x1400484af  mov     ebx, eax
0x1400484b1  test    eax, eax
0x1400484b3  jz      short loc_14004848E
0x1400484b5  jmp     short loc_1400484E1
0x1400484b7  mov     rcx, [rbp+ppvObject]
0x1400484bb  lea     rdx, aTarget; "target"
0x1400484c2  call    _anonymous_namespace___DfspLocateElement
0x1400484c7  cmp     eax, 490h
0x1400484cc  jz      short loc_1400484D5
0x1400484ce  mov     ebx, 0C00038CFh
0x1400484d3  jmp     short loc_1400484E1
0x1400484d5  mov     [r12], esi
0x1400484d9  mov     [r13+0], rdi
0x1400484dd  xor     edi, edi
0x1400484df  xor     ebx, ebx
0x1400484e1  lea     rsi, WPP_GLOBAL_Control
0x1400484e8  mov     rcx, rdi; Block
0x1400484eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400484f0  test    r15, r15
0x1400484f3  jz      short loc_140048504
0x1400484f5  mov     rax, [r15]
0x1400484f8  mov     rcx, r15
0x1400484fb  mov     rax, [rax+10h]
0x1400484ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048504  mov     rcx, [rbp+ppvObject]
0x140048508  test    rcx, rcx
0x14004850b  jz      short loc_140048519
0x14004850d  mov     rax, [rcx]
0x140048510  mov     rax, [rax+10h]
0x140048514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048519  cmp     cs:WPP_GLOBAL_Control, rsi
0x140048520  jz      short loc_140048552
0x140048522  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140048529  test    rcx, rcx
0x14004852c  jz      short loc_140048552
0x14004852e  test    byte ptr [rcx+1Ch], 20h
0x140048532  jz      short loc_140048552
0x140048534  cmp     byte ptr [rcx+19h], 2
0x140048538  jb      short loc_140048552
0x14004853a  mov     rcx, [rcx+10h]
0x14004853e  lea     r8, WPP_776a9413f9143c79b55c3fad11ed3a14_Traceguids
0x140048545  mov     edx, 0Dh
0x14004854a  mov     r9d, ebx
0x14004854d  call    WPP_SF_D
0x140048552  lea     r11, [rsp+50h+var_s0]
0x140048557  mov     eax, ebx
0x140048559  mov     rbx, [r11+30h]
0x14004855d  mov     rsi, [r11+38h]
0x140048561  mov     rdi, [r11+40h]
0x140048565  mov     rsp, r11
0x140048568  pop     r15
0x14004856a  pop     r14
0x14004856c  pop     r13
0x14004856e  pop     r12
0x140048570  pop     rbp
0x140048571  retn
```
