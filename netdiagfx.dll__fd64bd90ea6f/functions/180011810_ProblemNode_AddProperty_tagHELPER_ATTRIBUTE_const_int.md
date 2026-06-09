# ProblemNode::AddProperty(tagHELPER_ATTRIBUTE const &,int)

- ea: `0x180011810`
- end: `0x1800118c5`
- name: `?AddProperty@ProblemNode@@QEAAJAEBUtagHELPER_ATTRIBUTE@@H@Z`
- size: `181`
- prototype: `__int64 __fastcall(ProblemNode *this, const struct tagHELPER_ATTRIBUTE *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d8dc`
- `0x18000ec4c`

## callees

- `0x180008ca8`
- `0x180009f54`
- `0x180011810`
- `0x180011af0`
- `0x18002c802`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011831`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011831`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProblemNode::AddProperty(ProblemNode *this, const struct tagHELPER_ATTRIBUTE *a2)
{
  struct tagHELPER_ATTRIBUTE *v4; // rax
  struct tagHELPER_ATTRIBUTE *v5; // rdi
  unsigned int v6; // ebx
  struct tagHELPER_ATTRIBUTE *v8; // [rsp+20h] [rbp-48h] BYREF
  __int64 v9; // [rsp+28h] [rbp-40h]
  __int128 v10; // [rsp+30h] [rbp-38h] BYREF

  v10 = 0;
  v4 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(0x90u);
  v5 = v4;
  *(_QWORD *)&v10 = v4;
  v6 = -2147024882;
  if ( v4 )
  {
    memset_0(v4, 0, sizeof(struct tagHELPER_ATTRIBUTE));
    v6 = 0;
  }
  v8 = v5;
  v9 = 0x100000001LL;
  if ( !v6 )
  {
    v6 = CopyHelperAttribute(v5, a2);
    if ( !v6 )
    {
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        DWORD2(v10) = 0;
        std::vector<PropertyBagEntry>::push_back((char *)this + 104, &v10);
        v8 = 0;
        v9 = 0;
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
        {
          v6 = 14;
          __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_1800118A8);
        }
      }
    }
  }
  TNDFDeallocator<tagHELPER_ATTRIBUTE *,&void FreeHelperAttributes(tagHELPER_ATTRIBUTE *,unsigned long,int)>::~TNDFDeallocator<tagHELPER_ATTRIBUTE *,&void FreeHelperAttributes(tagHELPER_ATTRIBUTE *,unsigned long,int)>(&v8);
  return v6;
}

```

## disassembly

```asm
0x180011810  mov     [rsp+arg_10], r8d
0x180011815  push    rbx
0x180011816  push    rsi
0x180011817  push    rdi
0x180011818  push    r14
0x18001181a  sub     rsp, 48h
0x18001181e  mov     r14, rdx
0x180011821  mov     rsi, rcx
0x180011824  xorps   xmm0, xmm0
0x180011827  movups  [rsp+68h+var_38], xmm0
0x18001182c  mov     ecx, 90h; cb
0x180011831  call    cs:__imp_CoTaskMemAlloc
0x180011837  mov     rdi, rax
0x18001183a  mov     qword ptr [rsp+68h+var_38], rax
0x18001183f  mov     ebx, 8007000Eh
0x180011844  test    rax, rax
0x180011847  jz      short loc_18001185B
0x180011849  xor     edx, edx; Val
0x18001184b  mov     r8d, 90h; Size
0x180011851  mov     rcx, rax; void *
0x180011854  call    memset_0
0x180011859  xor     ebx, ebx
0x18001185b  mov     [rsp+68h+var_48], rdi
0x180011860  mov     eax, 1
0x180011865  mov     dword ptr [rsp+68h+var_40], eax
0x180011869  mov     dword ptr [rsp+68h+var_40+4], eax
0x18001186d  test    ebx, ebx
0x18001186f  jnz     short loc_1800118AF
0x180011871  mov     rdx, r14; struct tagHELPER_ATTRIBUTE *
0x180011874  mov     rcx, rdi; struct tagHELPER_ATTRIBUTE *
0x180011877  call    ?CopyHelperAttribute@@YAJPEAUtagHELPER_ATTRIBUTE@@PEBU1@@Z; CopyHelperAttribute(tagHELPER_ATTRIBUTE *,tagHELPER_ATTRIBUTE const *)
0x18001187c  mov     ebx, eax
0x18001187e  test    eax, eax
0x180011880  jnz     short loc_1800118AF
0x180011882  mov     dword ptr [rsp+68h+var_38+8], eax
0x180011886  lea     rcx, [rsi+68h]
0x18001188a  lea     rdx, [rsp+68h+var_38]
0x18001188f  call    ?push_back@?$vector@UPropertyBagEntry@@V?$allocator@UPropertyBagEntry@@@std@@@std@@QEAAXAEBUPropertyBagEntry@@@Z; std::vector<PropertyBagEntry>::push_back(PropertyBagEntry const &)
0x180011894  mov     [rsp+68h+var_48], 0
0x18001189d  mov     [rsp+68h+var_40], 0
0x1800118a6  jmp     short loc_1800118AF
0x1800118a8  mov     ebx, [rsp+68h+arg_10]
0x1800118af  lea     rcx, [rsp+68h+var_48]
0x1800118b4  call    ??1?$TNDFDeallocator@PEAUtagHELPER_ATTRIBUTE@@$1?FreeHelperAttributes@@YAXPEAU1@KH@Z@@QEAA@XZ; TNDFDeallocator<tagHELPER_ATTRIBUTE *,&FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)>::~TNDFDeallocator<tagHELPER_ATTRIBUTE *,&FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)>(void)
0x1800118b9  mov     eax, ebx
0x1800118bb  add     rsp, 48h
0x1800118bf  pop     r14
0x1800118c1  pop     rdi
0x1800118c2  pop     rsi
0x1800118c3  pop     rbx
0x1800118c4  retn
```
