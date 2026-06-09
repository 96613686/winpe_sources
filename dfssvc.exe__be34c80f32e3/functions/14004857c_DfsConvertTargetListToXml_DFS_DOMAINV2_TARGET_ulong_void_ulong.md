# DfsConvertTargetListToXml(_DFS_DOMAINV2_TARGET *,ulong,void * *,ulong *)

- ea: `0x14004857c`
- end: `0x140048794`
- name: `?DfsConvertTargetListToXml@@YAKPEAU_DFS_DOMAINV2_TARGET@@KPEAPEAXPEAK@Z`
- size: `536`
- prototype: `unsigned int __fastcall(struct _DFS_DOMAINV2_TARGET *, unsigned int, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140043690`

## callees

- `0x1400011c4`
- `0x140005a94`
- `0x1400096ac`
- `0x14004857c`
- `0x14004879c`
- `0x1400496a8`
- `0x140058a38`
- `0x14005e010`

## import_xrefs

- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x140048645`
- `XmlLite!CreateXmlWriterOutputWithEncodingName` at `0x140048645`
- `XmlLite!CreateXmlWriter` at `0x140048621`
- `XmlLite!CreateXmlWriter` at `0x140048621`

## pseudocode

```c
__int64 __fastcall DfsConvertTargetListToXml(
        struct _DFS_DOMAINV2_TARGET *a1,
        unsigned int a2,
        void **a3,
        unsigned int *a4)
{
  HRESULT MemoryStream; // eax
  unsigned int XmlDocument; // ebx
  void *ppvObject; // [rsp+38h] [rbp-18h] BYREF
  IXmlWriterOutput *ppOutput; // [rsp+40h] [rbp-10h] BYREF

  ppOutput = 0;
  ppvObject = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)pWppControl + 2), 14, WPP_776a9413f9143c79b55c3fad11ed3a14_Traceguids);
  }
  MemoryStream = anonymous_namespace_::DfsMemoryStream::_CreateMemoryStream(0, 0, 0);
  if ( MemoryStream < 0 )
    goto LABEL_14;
  MemoryStream = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( MemoryStream < 0 )
    goto LABEL_14;
  MemoryStream = CreateXmlWriterOutputWithEncodingName(0, 0, L"utf-16", &ppOutput);
  if ( MemoryStream < 0 )
    goto LABEL_14;
  MemoryStream = (*(__int64 (__fastcall **)(void *, IXmlWriterOutput *))(*(_QWORD *)ppvObject + 24LL))(
                   ppvObject,
                   ppOutput);
  if ( MemoryStream < 0 )
    goto LABEL_14;
  MemoryStream = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 1, 1);
  if ( MemoryStream < 0 )
    goto LABEL_14;
  XmlDocument = anonymous_namespace_::DfspGenerateXmlDocument(ppvObject, a1, a2);
  if ( XmlDocument )
    goto LABEL_15;
  MemoryStream = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 112LL))(ppvObject);
  if ( MemoryStream >= 0
    && (MemoryStream = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 248LL))(ppvObject), MemoryStream >= 0) )
  {
    XmlDocument = 0;
    *a3 = (void *)MEMORY[0x10];
    *a4 = MEMORY[0x24];
  }
  else
  {
LABEL_14:
    XmlDocument = DfsGetErrorFromHr(MemoryStream);
  }
LABEL_15:
  if ( ppOutput )
    ((void (__fastcall *)(IXmlWriterOutput *))ppOutput->lpVtbl->Release)(ppOutput);
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 15, WPP_776a9413f9143c79b55c3fad11ed3a14_Traceguids, XmlDocument);
  }
  return XmlDocument;
}

```

## disassembly

```asm
0x14004857c  mov     rax, rsp
0x14004857f  mov     [rax+8], rbx
0x140048583  mov     [rax+10h], rsi
0x140048587  mov     [rax+18h], rdi
0x14004858b  mov     [rax+20h], r13
0x14004858f  push    rbp
0x140048590  push    r14
0x140048592  push    r15
0x140048594  mov     rbp, rsp
0x140048597  sub     rsp, 50h
0x14004859b  and     [rbp+ppOutput], 0
0x1400485a0  mov     r14, r9
0x1400485a3  and     [rbp+pOutputStream], 0
0x1400485a8  mov     r15, r8
0x1400485ab  and     [rbp+ppvObject], 0
0x1400485b0  mov     ebx, edx
0x1400485b2  mov     rsi, rcx
0x1400485b5  lea     r13, WPP_GLOBAL_Control
0x1400485bc  cmp     cs:WPP_GLOBAL_Control, r13
0x1400485c3  jz      short loc_1400485F2
0x1400485c5  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400485cc  test    rcx, rcx
0x1400485cf  jz      short loc_1400485F2
0x1400485d1  test    byte ptr [rcx+1Ch], 20h
0x1400485d5  jz      short loc_1400485F2
0x1400485d7  cmp     byte ptr [rcx+19h], 2
0x1400485db  jb      short loc_1400485F2
0x1400485dd  mov     rcx, [rcx+10h]
0x1400485e1  lea     r8, WPP_776a9413f9143c79b55c3fad11ed3a14_Traceguids
0x1400485e8  mov     edx, 0Eh
0x1400485ed  call    WPP_SF_
0x1400485f2  lea     rax, [rbp+pOutputStream]
0x1400485f6  xor     r8d, r8d
0x1400485f9  xor     edx, edx
0x1400485fb  mov     [rsp+50h+var_30], rax
0x140048600  xor     ecx, ecx
0x140048602  call    _anonymous_namespace___DfsMemoryStream___CreateMemoryStream
0x140048607  mov     rdi, [rbp+pOutputStream]
0x14004860b  test    eax, eax
0x14004860d  js      loc_1400486CD
0x140048613  xor     r8d, r8d; pMalloc
0x140048616  lea     rdx, [rbp+ppvObject]; ppvObject
0x14004861a  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x140048621  call    cs:__imp_CreateXmlWriter
0x140048628  nop     dword ptr [rax+rax+00h]
0x14004862d  test    eax, eax
0x14004862f  js      loc_1400486CD
0x140048635  lea     r9, [rbp+ppOutput]; ppOutput
0x140048639  xor     edx, edx; pMalloc
0x14004863b  lea     r8, pwszEncodingName; "utf-16"
0x140048642  mov     rcx, rdi; pOutputStream
0x140048645  call    cs:__imp_CreateXmlWriterOutputWithEncodingName
0x14004864c  nop     dword ptr [rax+rax+00h]
0x140048651  test    eax, eax
0x140048653  js      short loc_1400486CD
0x140048655  mov     rcx, [rbp+ppvObject]
0x140048659  mov     rdx, [rbp+ppOutput]
0x14004865d  mov     rax, [rcx]
0x140048660  mov     rax, [rax+18h]
0x140048664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048669  test    eax, eax
0x14004866b  js      short loc_1400486CD
0x14004866d  mov     rcx, [rbp+ppvObject]
0x140048671  mov     edx, 1
0x140048676  mov     r8d, edx
0x140048679  mov     rax, [rcx]
0x14004867c  mov     rax, [rax+28h]
0x140048680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048685  test    eax, eax
0x140048687  js      short loc_1400486CD
0x140048689  mov     rcx, [rbp+ppvObject]
0x14004868d  mov     r8d, ebx
0x140048690  mov     rdx, rsi
0x140048693  call    _anonymous_namespace___DfspGenerateXmlDocument
0x140048698  mov     ebx, eax
0x14004869a  test    eax, eax
0x14004869c  jnz     short loc_1400486DA
0x14004869e  mov     rcx, [rbp+ppvObject]
0x1400486a2  mov     rax, [rcx]
0x1400486a5  mov     rax, [rax+70h]
0x1400486a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400486ae  test    eax, eax
0x1400486b0  js      short loc_1400486CD
0x1400486b2  mov     rcx, [rbp+ppvObject]
0x1400486b6  mov     rax, [rcx]
0x1400486b9  mov     rax, [rax+0F8h]
0x1400486c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400486c5  test    eax, eax
0x1400486c7  jns     loc_140048780
0x1400486cd  mov     ecx, eax; int
0x1400486cf  call    ?DfsGetErrorFromHr@@YAKJ@Z; DfsGetErrorFromHr(long)
0x1400486d4  mov     ebx, eax
0x1400486d6  test    eax, eax
0x1400486d8  jz      short loc_1400486E8
0x1400486da  test    rdi, rdi
0x1400486dd  jz      short loc_1400486E8
0x1400486df  mov     rcx, [rdi+10h]; Block
0x1400486e3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400486e8  mov     rcx, [rbp+ppOutput]
0x1400486ec  test    rcx, rcx
0x1400486ef  jz      short loc_1400486FD
0x1400486f1  mov     rax, [rcx]
0x1400486f4  mov     rax, [rax+10h]
0x1400486f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400486fd  mov     rcx, [rbp+ppvObject]
0x140048701  test    rcx, rcx
0x140048704  jz      short loc_140048712
0x140048706  mov     rax, [rcx]
0x140048709  mov     rax, [rax+10h]
0x14004870d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048712  test    rdi, rdi
0x140048715  jz      short loc_140048726
0x140048717  mov     rax, [rdi]
0x14004871a  mov     rcx, rdi
0x14004871d  mov     rax, [rax+10h]
0x140048721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048726  cmp     cs:WPP_GLOBAL_Control, r13
0x14004872d  jz      short loc_14004875F
0x14004872f  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140048736  test    rcx, rcx
0x140048739  jz      short loc_14004875F
0x14004873b  test    byte ptr [rcx+1Ch], 20h
0x14004873f  jz      short loc_14004875F
0x140048741  cmp     byte ptr [rcx+19h], 2
0x140048745  jb      short loc_14004875F
0x140048747  mov     rcx, [rcx+10h]
0x14004874b  lea     r8, WPP_776a9413f9143c79b55c3fad11ed3a14_Traceguids
0x140048752  mov     edx, 0Fh
0x140048757  mov     r9d, ebx
0x14004875a  call    WPP_SF_D
0x14004875f  lea     r11, [rsp+50h+var_s0]
0x140048764  mov     eax, ebx
0x140048766  mov     rbx, [r11+20h]
0x14004876a  mov     rsi, [r11+28h]
0x14004876e  mov     rdi, [r11+30h]
0x140048772  mov     r13, [r11+38h]
0x140048776  mov     rsp, r11
0x140048779  pop     r15
0x14004877b  pop     r14
0x14004877d  pop     rbp
0x14004877e  retn
0x140048780  mov     rax, [rdi+10h]
0x140048784  xor     ebx, ebx
0x140048786  mov     [r15], rax
0x140048789  mov     eax, [rdi+24h]
0x14004878c  mov     [r14], eax
0x14004878f  jmp     loc_1400486E8
```
