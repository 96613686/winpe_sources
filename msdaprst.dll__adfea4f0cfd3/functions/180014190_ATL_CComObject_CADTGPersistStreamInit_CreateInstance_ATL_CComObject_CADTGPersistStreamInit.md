# ATL::CComObject<CADTGPersistStreamInit>::CreateInstance(ATL::CComObject<CADTGPersistStreamInit> * *)

- ea: `0x180014190`
- end: `0x180014256`
- name: `?CreateInstance@?$CComObject@VCADTGPersistStreamInit@@@ATL@@SAJPEAPEAV12@@Z`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014bd0`

## callees

- `0x180001dd4`
- `0x18000a3d4`
- `0x180014190`
- `0x18001ae88`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CADTGPersistStreamInit>::CreateInstance(unsigned __int8 **a1, unsigned int a2)
{
  __int64 result; // rax
  unsigned __int8 *v4; // rax
  unsigned __int8 *v5; // rdi
  unsigned int v6; // [rsp+20h] [rbp-18h] BYREF

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v4 = MMMAlloc(0x40u, a2);
  try
  {
    v5 = v4;
    if ( v4 )
    {
      ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>((_DWORD *)v4 + 2);
      *(_QWORD *)v5 = &CADTGPersistStreamInit::`vftable';
      *((_DWORD *)v5 + 8) = 0;
      *((_QWORD *)v5 + 3) = &CADTGPersistStreamInit::CNotUpdt_BidGeneric::`vftable';
      *((_DWORD *)v5 + 8) = bidObtainItemIDW(
                              `CADTGPersistStreamInit::CNotUpdt_BidGeneric::BidObtainID'::`7'::_bidPtrSA_051_525[0],
                              v5 + 24);
      *((_QWORD *)v5 + 7) = 0;
      *((_WORD *)v5 + 22) = 0;
      *((_DWORD *)v5 + 10) = 0;
      *(_QWORD *)v5 = &ATL::CComObject<CADTGPersistStreamInit>::`vftable';
      _InterlockedIncrement(&dword_1800464E8);
    }
    else
    {
      v5 = 0;
    }
    result = v5 == 0 ? 0x8007000E : 0;
    *a1 = v5;
  }
  catch ( long v6 )
  {
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180014190  mov     [rsp+arg_8], rbx
0x180014195  mov     [rsp+arg_10], rsi
0x18001419a  push    rdi
0x18001419b  sub     rsp, 30h
0x18001419f  mov     rsi, rcx
0x1800141a2  test    rcx, rcx
0x1800141a5  jnz     short loc_1800141B1
0x1800141a7  mov     eax, 80004003h
0x1800141ac  jmp     loc_180014245
0x1800141b1  mov     qword ptr [rcx], 0
0x1800141b8  mov     ecx, 40h ; '@'; unsigned int
0x1800141bd  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800141c2  mov     rdi, rax
0x1800141c5  mov     [rsp+38h+arg_0], rax
0x1800141ca  test    rax, rax
0x1800141cd  jz      short loc_18001422B
0x1800141cf  lea     rcx, [rax+8]
0x1800141d3  call    ??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x1800141d8  lea     rax, ??_7CADTGPersistStreamInit@@6B@; const CADTGPersistStreamInit::`vftable'
0x1800141df  mov     [rdi], rax
0x1800141e2  mov     dword ptr [rdi+20h], 0
0x1800141e9  lea     rax, ??_7CNotUpdt_BidGeneric@CADTGPersistStreamInit@@6B@; const CADTGPersistStreamInit::CNotUpdt_BidGeneric::`vftable'
0x1800141f0  mov     [rdi+18h], rax
0x1800141f4  lea     rdx, [rdi+18h]
0x1800141f8  mov     rcx, cs:?_bidPtrSA_051_525@?6??BidObtainID@CNotUpdt_BidGeneric@CADTGPersistStreamInit@@AEAAHPEBX@Z@4REBGEB; ushort const * const `CADTGPersistStreamInit::CNotUpdt_BidGeneric::BidObtainID(void const *)'::`7'::_bidPtrSA_051_525
0x1800141ff  call    _bidObtainItemIDW
0x180014204  mov     [rdi+20h], eax
0x180014207  mov     qword ptr [rdi+38h], 0
0x18001420f  xor     eax, eax
0x180014211  mov     [rdi+2Ch], ax
0x180014215  mov     [rdi+28h], eax
0x180014218  lea     rax, ??_7?$CComObject@VCADTGPersistStreamInit@@@ATL@@6B@; const ATL::CComObject<CADTGPersistStreamInit>::`vftable'
0x18001421f  mov     [rdi], rax
0x180014222  lock inc cs:dword_1800464E8
0x180014229  jmp     short loc_18001422D
0x18001422b  xor     edi, edi
0x18001422d  mov     rax, rdi
0x180014230  neg     rax
0x180014233  sbb     eax, eax
0x180014235  not     eax
0x180014237  and     eax, 8007000Eh
0x18001423c  mov     [rsi], rdi
0x18001423f  jmp     short loc_180014245
0x180014241  mov     eax, [rsp+38h+var_18]
0x180014245  mov     rbx, [rsp+38h+arg_8]
0x18001424a  mov     rsi, [rsp+38h+arg_10]
0x18001424f  add     rsp, 30h
0x180014253  pop     rdi
0x180014254  retn
```
