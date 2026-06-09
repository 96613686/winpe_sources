# LCIEGetStreamFromMessage(ulong,bool,IStream * *)

- ea: `0x180076704`
- end: `0x1800767cf`
- name: `?LCIEGetStreamFromMessage@@YAJK_NPEAPEAUIStream@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(unsigned int, bool, struct IStream **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001c1b4`

## callees

- `0x18002e25c`
- `0x1800766cc`
- `0x180076704`

## import_xrefs

- `SHCORE!SHCreateMemStream` at `0x18007678b`
- `SHCORE!SHCreateMemStream` at `0x18007678b`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_MinSize@@YA_NKKPEAK@Z` at `0x18007675b`
- `edgeIso!__imp_?VerifyUntrusted_IsoMessage_MinSize@@YA_NKKPEAK@Z` at `0x18007675b`
- `edgeIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x180076738`
- `edgeIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x180076738`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LCIEGetStreamFromMessage(unsigned int a1, char a2, struct IStream **a3)
{
  int MessageBufferAddress; // ebx
  IStream *v6; // rax
  struct IStream *v7; // rax
  struct _IsoMessage *v9; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v10; // [rsp+68h] [rbp+28h] BYREF
  struct IStream *v11; // [rsp+78h] [rbp+38h] BYREF

  LOBYTE(v10) = a2;
  v9 = 0;
  MessageBufferAddress = IsoGetMessageBufferAddress(a1, 1, 0, &v9, 0);
  if ( MessageBufferAddress >= 0 )
  {
    MessageBufferAddress = -2147467259;
    v10 = 0;
    if ( VerifyUntrusted_IsoMessage_MinSize(a1, 0x28u, &v10) && *((unsigned int *)v9 + 8) + 40LL == v10 )
    {
      v11 = 0;
      v6 = SHCreateMemStream((const BYTE *)v9 + 36, *((_DWORD *)v9 + 8));
      ATL::CComPtr<IStream>::Attach(&v11, v6);
      v7 = v11;
      if ( v11 )
      {
        MessageBufferAddress = 0;
        v11 = 0;
        *a3 = v7;
      }
      else
      {
        MessageBufferAddress = -2147024882;
      }
      ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(&v11);
    }
  }
  return (unsigned int)MessageBufferAddress;
}

```

## disassembly

```asm
0x180076704  mov     [rsp-18h+arg_0], rbx
0x180076709  mov     byte ptr [rsp-18h+arg_8], dl
0x18007670d  push    rbp
0x18007670e  push    rsi
0x18007670f  push    rdi
0x180076710  mov     rbp, rsp
0x180076713  sub     rsp, 40h
0x180076717  mov     rsi, r8
0x18007671a  mov     edi, ecx
0x18007671c  mov     [rbp+var_10], 0
0x180076724  mov     [rsp+40h+var_20], 0
0x18007672d  lea     r9, [rbp+var_10]
0x180076731  xor     r8d, r8d
0x180076734  lea     edx, [r8+1]
0x180076738  call    cs:__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z; IsoGetMessageBufferAddress(ulong,int,ulong *,_IsoMessage * *,ulong *)
0x18007673e  mov     ebx, eax
0x180076740  test    eax, eax
0x180076742  js      short loc_1800767C0
0x180076744  mov     ebx, 80004005h
0x180076749  mov     [rbp+arg_8], 0
0x180076750  lea     r8, [rbp+arg_8]
0x180076754  mov     edx, 28h ; '('
0x180076759  mov     ecx, edi
0x18007675b  call    cs:__imp_?VerifyUntrusted_IsoMessage_MinSize@@YA_NKKPEAK@Z; VerifyUntrusted_IsoMessage_MinSize(ulong,ulong,ulong *)
0x180076761  test    al, al
0x180076763  jz      short loc_1800767C0
0x180076765  mov     rax, [rbp+var_10]
0x180076769  mov     ecx, [rax+20h]
0x18007676c  add     rcx, 28h ; '('
0x180076770  mov     eax, [rbp+arg_8]
0x180076773  cmp     rcx, rax
0x180076776  jnz     short loc_1800767C0
0x180076778  mov     [rbp+arg_18], 0
0x180076780  mov     rdx, [rbp+var_10]
0x180076784  lea     rcx, [rdx+24h]; pInit
0x180076788  mov     edx, [rdx+20h]; cbInit
0x18007678b  call    cs:__imp_SHCreateMemStream
0x180076791  mov     rdx, rax
0x180076794  lea     rcx, [rbp+arg_18]
0x180076798  call    ?Attach@?$CComPtr@UIStream@@@ATL@@QEAAXPEAUIStream@@@Z; ATL::CComPtr<IStream>::Attach(IStream *)
0x18007679d  mov     rax, [rbp+arg_18]
0x1800767a1  test    rax, rax
0x1800767a4  jz      short loc_1800767B1
0x1800767a6  xor     ebx, ebx
0x1800767a8  mov     [rbp+arg_18], rbx
0x1800767ac  mov     [rsi], rax
0x1800767af  jmp     short loc_1800767B6
0x1800767b1  mov     ebx, 8007000Eh
0x1800767b6  lea     rcx, [rbp+arg_18]
0x1800767ba  call    ??1?$CComPtrBase@UIStream@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IStream>::~CComPtrBase<IStream>(void)
0x1800767bf  nop
0x1800767c0  mov     eax, ebx
0x1800767c2  mov     rbx, [rsp+40h+arg_0]
0x1800767c7  add     rsp, 40h
0x1800767cb  pop     rdi
0x1800767cc  pop     rsi
0x1800767cd  pop     rbp
0x1800767ce  retn
```
