# CReFsVolume::FinalRelease(void)

- ea: `0x180062bd0`
- end: `0x180062ce8`
- name: `?FinalRelease@CReFsVolume@@QEAAJXZ`
- size: `280`
- prototype: `__int64 __fastcall(CReFsVolume *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800622c0`
- `0x180062a54`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001fed8`
- `0x180024afc`
- `0x180062bd0`
- `0x180062cf0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062c35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062c95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062c35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062c95`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CReFsVolume::FinalRelease(CReFsVolume *this)
{
  CFatVolume *v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rcx
  int Next; // ebx
  __int64 v6; // rbx
  int v8; // [rsp+20h] [rbp-40h] BYREF
  __int16 v9; // [rsp+24h] [rbp-3Ch]
  __int16 v10; // [rsp+26h] [rbp-3Ah]
  struct _QUEUED_DIR *v11; // [rsp+80h] [rbp+20h] BYREF
  __int64 v12; // [rsp+88h] [rbp+28h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "CReFsVolume::FinalRelease", 303, 1);
  v12 = 0;
  while ( 1 )
  {
    v3 = *((_QWORD *)this + 129);
    if ( !v3 )
      break;
    v11 = (struct _QUEUED_DIR *)*((_QWORD *)this + 129);
    *((_QWORD *)this + 129) = *(_QWORD *)(v3 + 8);
    CFatVolume::FreeDir(v2, &v11);
  }
  CoTaskMemFree(*((LPVOID *)this + 132));
  *((_QWORD *)this + 132) = 0;
  CVolume::_DestroyVars(this);
  v4 = *((_QWORD *)this + 135);
  *(_QWORD *)(v4 + 40) = 0;
  Next = CBulkAllocator<CReFsFile>::GetNext(v4, &v11, &v12);
  v8 = Next;
  if ( Next >= 0 )
  {
    v9 = 322;
    while ( Next != 1 )
    {
      v6 = v12;
      CoTaskMemFree(*(LPVOID *)(v12 + 16));
      *(_QWORD *)(v6 + 16) = 0;
      Next = CBulkAllocator<CReFsFile>::GetNext(*((_QWORD *)this + 135), &v11, &v12);
      v8 = Next;
      if ( Next < 0 )
      {
        v10 = 327;
        break;
      }
      v9 = 327;
    }
  }
  else
  {
    v10 = 322;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return (unsigned int)Next;
}

```

## disassembly

```asm
0x180062bd0  mov     [rsp-18h+arg_10], rbx
0x180062bd5  push    rbp
0x180062bd6  push    rdi
0x180062bd7  push    r14
0x180062bd9  mov     rbp, rsp
0x180062bdc  sub     rsp, 60h
0x180062be0  mov     rdi, rcx
0x180062be3  mov     r9d, 1; unsigned __int16
0x180062be9  mov     r8d, 12Fh; unsigned __int16
0x180062bef  lea     rdx, aCrefsvolumeFin; "CReFsVolume::FinalRelease"
0x180062bf6  lea     rcx, [rbp+var_40]; this
0x180062bfa  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180062bff  nop
0x180062c00  mov     [rbp+arg_8], 0
0x180062c08  jmp     short loc_180062C22
0x180062c0a  mov     [rbp+arg_0], rax
0x180062c0e  mov     rax, [rax+8]
0x180062c12  mov     [rdi+408h], rax
0x180062c19  lea     rdx, [rbp+arg_0]; struct _QUEUED_DIR **
0x180062c1d  call    ?FreeDir@CFatVolume@@AEAAXPEAPEAU_QUEUED_DIR@@@Z; CFatVolume::FreeDir(_QUEUED_DIR * *)
0x180062c22  mov     rax, [rdi+408h]
0x180062c29  test    rax, rax
0x180062c2c  jnz     short loc_180062C0A
0x180062c2e  mov     rcx, [rdi+420h]; pv
0x180062c35  call    cs:__imp_CoTaskMemFree
0x180062c3b  mov     qword ptr [rdi+420h], 0
0x180062c46  mov     rcx, rdi; this
0x180062c49  call    ?_DestroyVars@CVolume@@IEAAJXZ; CVolume::_DestroyVars(void)
0x180062c4e  mov     rcx, [rdi+438h]
0x180062c55  mov     qword ptr [rcx+28h], 0
0x180062c5d  lea     r8, [rbp+arg_8]
0x180062c61  lea     rdx, [rbp+arg_0]
0x180062c65  call    ?GetNext@?$CBulkAllocator@VCReFsFile@@@@QEAAJPEAKPEAPEAVCReFsFile@@@Z; CBulkAllocator<CReFsFile>::GetNext(ulong *,CReFsFile * *)
0x180062c6a  mov     ebx, eax
0x180062c6c  mov     [rbp+var_40], eax
0x180062c6f  test    eax, eax
0x180062c71  mov     eax, 142h
0x180062c76  jns     short loc_180062C7E
0x180062c78  mov     [rbp+var_3A], ax
0x180062c7c  jmp     short loc_180062CCC
0x180062c7e  mov     [rbp+var_3C], ax
0x180062c82  mov     r14d, 147h
0x180062c88  cmp     ebx, 1
0x180062c8b  jz      short loc_180062CCC
0x180062c8d  mov     rbx, [rbp+arg_8]
0x180062c91  mov     rcx, [rbx+10h]; pv
0x180062c95  call    cs:__imp_CoTaskMemFree
0x180062c9b  mov     qword ptr [rbx+10h], 0
0x180062ca3  lea     r8, [rbp+arg_8]
0x180062ca7  lea     rdx, [rbp+arg_0]
0x180062cab  mov     rcx, [rdi+438h]
0x180062cb2  call    ?GetNext@?$CBulkAllocator@VCReFsFile@@@@QEAAJPEAKPEAPEAVCReFsFile@@@Z; CBulkAllocator<CReFsFile>::GetNext(ulong *,CReFsFile * *)
0x180062cb7  mov     ebx, eax
0x180062cb9  mov     [rbp+var_40], eax
0x180062cbc  test    eax, eax
0x180062cbe  js      short loc_180062CC7
0x180062cc0  mov     [rbp+var_3C], r14w
0x180062cc5  jmp     short loc_180062C88
0x180062cc7  mov     [rbp+var_3A], r14w
0x180062ccc  lea     rcx, [rbp+var_40]; this
0x180062cd0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180062cd5  mov     eax, ebx
0x180062cd7  mov     rbx, [rsp+60h+arg_10]
0x180062cdf  add     rsp, 60h
0x180062ce3  pop     r14
0x180062ce5  pop     rdi
0x180062ce6  pop     rbp
0x180062ce7  retn
```
