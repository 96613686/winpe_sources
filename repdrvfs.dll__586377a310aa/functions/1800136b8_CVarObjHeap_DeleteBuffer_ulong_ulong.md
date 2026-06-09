# CVarObjHeap::DeleteBuffer(ulong,ulong)

- ea: `0x1800136b8`
- end: `0x180013874`
- name: `?DeleteBuffer@CVarObjHeap@@QEAAKKK@Z`
- size: `444`
- prototype: `__int64 __fastcall(CPageFile **this, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013048`
- `0x180028590`
- `0x180030a90`

## callees

- `0x1800012b8`
- `0x18000e000`
- `0x18000f8a0`
- `0x18000f8f0`
- `0x18000fd30`
- `0x1800136b8`
- `0x1800138f4`
- `0x1800141f0`
- `0x1800241e4`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800136f7`
- `wbemcomn!GetMemLogObject` at `0x1800137f0`
- `wbemcomn!GetMemLogObject` at `0x1800136f7`
- `wbemcomn!GetMemLogObject` at `0x1800137f0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013702`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800137fb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013702`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800137fb`

## pseudocode

```c
__int64 __fastcall CVarObjHeap::DeleteBuffer(CPageFile **this, unsigned int a2, unsigned int a3)
{
  __int64 v4; // rdi
  unsigned int Page; // ebx
  unsigned int v7; // r8d
  CMemoryLog *MemLogObject; // rax
  __int64 v9; // r9
  unsigned __int8 **v10; // rax
  unsigned int v11; // edx
  CMemoryLog *v12; // rax
  MemoryPage *v14[4]; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v15; // [rsp+70h] [rbp+20h] BYREF
  MemoryPage *v16; // [rsp+88h] [rbp+38h] BYREF

  v4 = a2;
  v16 = 0;
  v14[1] = (MemoryPage *)&v16;
  Page = CPageFile::GetPage(*this, a2, a3, &v16);
  if ( Page )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, Page);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids, Page);
    }
  }
  else
  {
    v9 = *((_QWORD *)v16 + 2);
    if ( *(_DWORD *)(v9 + 8) <= 0x1FE0u )
    {
      v10 = (unsigned __int8 **)MemoryPage::Copy(v16);
      v14[0] = (MemoryPage *)v10;
      if ( !v10 )
        Page = 14;
      v14[2] = (MemoryPage *)v14;
      v15 = 0;
      if ( Page
        || (Page = CVarObjHeap::RemoveFromPage((CVarObjHeap *)&v15, v11, a3, v10[2], &v15)) != 0
        || (*(_DWORD *)(*((_QWORD *)*this + 41) + 24 * v4 + 8) += v15 + 16,
            MemoryPage::AddRef(v14[0]),
            Page = CPageFile::PutPage(*this, v4, 0, v14[0]),
            *((_DWORD *)this + 2) = v4,
            Page) )
      {
        v12 = GetMemLogObject();
        CMemoryLog::Write(v12, Page);
      }
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids, Page);
      }
      if ( v14[0] )
        MemoryPage::Release(v14[0]);
      v14[0] = 0;
    }
    else
    {
      Page = CVarObjHeap::DeleteMultiPageBuffer((CVarObjHeap *)this, v4, v7, (unsigned __int8 *)v9);
    }
  }
  if ( v16 )
    MemoryPage::Release(v16);
  return Page;
}

```

## disassembly

```asm
0x1800136b8  mov     [rsp-18h+arg_8], rbx
0x1800136bd  mov     [rsp-18h+arg_10], rsi
0x1800136c2  push    rbp
0x1800136c3  push    rdi
0x1800136c4  push    r14
0x1800136c6  mov     rbp, rsp
0x1800136c9  sub     rsp, 50h
0x1800136cd  mov     r14d, r8d
0x1800136d0  mov     edi, edx
0x1800136d2  mov     rsi, rcx
0x1800136d5  mov     [rbp+arg_18], 0
0x1800136dd  lea     rax, [rbp+arg_18]
0x1800136e1  mov     [rbp+var_18], rax
0x1800136e5  lea     r9, [rbp+arg_18]; struct MemoryPage **
0x1800136e9  mov     rcx, [rcx]; this
0x1800136ec  call    ?GetPage@CPageFile@@QEAAKKKPEAPEAVMemoryPage@@@Z; CPageFile::GetPage(ulong,ulong,MemoryPage * *)
0x1800136f1  mov     ebx, eax
0x1800136f3  test    eax, eax
0x1800136f5  jz      short loc_180013750
0x1800136f7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800136fd  mov     edx, ebx
0x1800136ff  mov     rcx, rax
0x180013702  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013708  lea     rax, WPP_GLOBAL_Control
0x18001370f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013716  cmp     rcx, rax
0x180013719  jz      loc_18001384F
0x18001371f  test    byte ptr [rcx+1Ch], 1
0x180013723  jz      loc_18001384F
0x180013729  cmp     byte ptr [rcx+19h], 2
0x18001372d  jb      loc_18001384F
0x180013733  mov     edx, 12h
0x180013738  mov     r9d, ebx
0x18001373b  lea     r8, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids
0x180013742  mov     rcx, [rcx+10h]
0x180013746  call    WPP_SF_d
0x18001374b  jmp     loc_18001384F
0x180013750  mov     rcx, [rbp+arg_18]; this
0x180013754  mov     r9, [rcx+10h]; unsigned __int8 *
0x180013758  cmp     dword ptr [r9+8], 1FE0h
0x180013760  jbe     short loc_180013773
0x180013762  mov     edx, edi; unsigned int
0x180013764  mov     rcx, rsi; this
0x180013767  call    ?DeleteMultiPageBuffer@CVarObjHeap@@IEAAKKKPEAE@Z; CVarObjHeap::DeleteMultiPageBuffer(ulong,ulong,uchar *)
0x18001376c  mov     ebx, eax
0x18001376e  jmp     loc_18001384F
0x180013773  call    ?Copy@MemoryPage@@QEAAPEAV1@XZ; MemoryPage::Copy(void)
0x180013778  mov     [rbp+var_20], rax
0x18001377c  mov     ecx, 0Eh
0x180013781  test    rax, rax
0x180013784  cmovz   ebx, ecx
0x180013787  lea     rcx, [rbp+var_20]
0x18001378b  mov     [rbp+var_10], rcx
0x18001378f  mov     [rbp+arg_0], 0
0x180013796  test    ebx, ebx
0x180013798  jnz     short loc_1800137F0
0x18001379a  lea     rcx, [rbp+arg_0]; this
0x18001379e  mov     [rsp+50h+var_30], rcx; unsigned int *
0x1800137a3  mov     r9, [rax+10h]; unsigned __int8 *
0x1800137a7  mov     r8d, r14d; unsigned int
0x1800137aa  call    ?RemoveFromPage@CVarObjHeap@@IEAAKKKPEAEPEAK@Z; CVarObjHeap::RemoveFromPage(ulong,ulong,uchar *,ulong *)
0x1800137af  mov     ebx, eax
0x1800137b1  test    eax, eax
0x1800137b3  jnz     short loc_1800137F0
0x1800137b5  lea     rdx, [rdi+rdi*2]
0x1800137b9  mov     rax, [rsi]
0x1800137bc  mov     rcx, [rax+148h]
0x1800137c3  mov     eax, [rbp+arg_0]
0x1800137c6  add     eax, 10h
0x1800137c9  add     [rcx+rdx*8+8], eax
0x1800137cd  mov     rcx, [rbp+var_20]; this
0x1800137d1  call    ?AddRef@MemoryPage@@QEAAJXZ; MemoryPage::AddRef(void)
0x1800137d6  mov     r9, [rbp+var_20]; struct MemoryPage *
0x1800137da  xor     r8d, r8d; unsigned int
0x1800137dd  mov     edx, edi; unsigned int
0x1800137df  mov     rcx, [rsi]; this
0x1800137e2  call    ?PutPage@CPageFile@@QEAAKKKPEAVMemoryPage@@@Z; CPageFile::PutPage(ulong,ulong,MemoryPage *)
0x1800137e7  mov     ebx, eax
0x1800137e9  mov     [rsi+8], edi
0x1800137ec  test    eax, eax
0x1800137ee  jz      short loc_180013801
0x1800137f0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800137f6  mov     edx, ebx
0x1800137f8  mov     rcx, rax
0x1800137fb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013801  lea     rax, WPP_GLOBAL_Control
0x180013808  mov     rcx, cs:WPP_GLOBAL_Control
0x18001380f  cmp     rcx, rax
0x180013812  jz      short loc_180013839
0x180013814  test    byte ptr [rcx+1Ch], 1
0x180013818  jz      short loc_180013839
0x18001381a  cmp     byte ptr [rcx+19h], 2
0x18001381e  jb      short loc_180013839
0x180013820  mov     edx, 13h
0x180013825  mov     r9d, ebx
0x180013828  lea     r8, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids
0x18001382f  mov     rcx, [rcx+10h]
0x180013833  call    WPP_SF_d
0x180013838  nop
0x180013839  mov     rcx, [rbp+var_20]; this
0x18001383d  test    rcx, rcx
0x180013840  jz      short loc_180013847
0x180013842  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x180013847  mov     [rbp+var_20], 0
0x18001384f  mov     rcx, [rbp+arg_18]; this
0x180013853  test    rcx, rcx
0x180013856  jz      short loc_18001385D
0x180013858  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x18001385d  mov     eax, ebx
0x18001385f  lea     r11, [rsp+50h+var_s0]
0x180013864  mov     rbx, [r11+28h]
0x180013868  mov     rsi, [r11+30h]
0x18001386c  mov     rsp, r11
0x18001386f  pop     r14
0x180013871  pop     rdi
0x180013872  pop     rbp
0x180013873  retn
```
