# CReFsVolume::RemoveFile(ulong)

- ea: `0x1800630d0`
- end: `0x1800631de`
- name: `?RemoveFile@CReFsVolume@@UEAAJK@Z`
- size: `270`
- prototype: `__int64 __fastcall(CReFsVolume *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x180006bf8`
- `0x180008530`
- `0x18000ad50`
- `0x180028ff0`
- `0x1800630d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063186`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063186`

## string_xrefs

- `0x1800630f0`: `CReFsVolume::RemoveFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CReFsVolume::RemoveFile(CReFsVolume *this, unsigned int a2)
{
  __int16 v4; // ax
  int Element; // ebx
  unsigned int *v6; // rdi
  int v8; // [rsp+20h] [rbp-40h] BYREF
  __int16 v9; // [rsp+24h] [rbp-3Ch]
  __int16 v10; // [rsp+26h] [rbp-3Ah]
  unsigned int v11; // [rsp+88h] [rbp+28h] BYREF
  unsigned int *v12; // [rsp+90h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "CReFsVolume::RemoveFile", 631, 1);
  v12 = 0;
  v11 = a2;
  v4 = 635;
  if ( a2 )
  {
    v8 = 0;
    v9 = 635;
    Element = CBulkAllocator<CReFsFile>::GetElement(*((_QWORD *)this + 135), &v11, &v12);
    v8 = Element;
    v4 = 637;
    if ( Element >= 0 )
    {
      v9 = 637;
      v6 = v12;
      if ( v12 && *v12 )
      {
        Element = CVolume::_FreeExtents(this, v12);
        v8 = Element;
        v4 = 641;
        if ( Element < 0 )
          goto LABEL_3;
        v9 = 641;
      }
      CoTaskMemFree(*((LPVOID *)v6 + 2));
      *((_QWORD *)v6 + 2) = 0;
      Element = CBulkAllocator<_CExtent>::Free(*((_QWORD *)this + 135), &v11);
      v8 = Element;
      v4 = 648;
      if ( Element >= 0 )
      {
        v9 = 648;
        v8 = 0;
        Element = 0;
        goto LABEL_11;
      }
    }
  }
  else
  {
    Element = -2147024809;
    v8 = -2147024809;
  }
LABEL_3:
  v10 = v4;
LABEL_11:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return (unsigned int)Element;
}

```

## disassembly

```asm
0x1800630d0  mov     [rsp-18h+arg_0], rbx
0x1800630d5  push    rbp
0x1800630d6  push    rsi
0x1800630d7  push    rdi
0x1800630d8  mov     rbp, rsp
0x1800630db  sub     rsp, 60h
0x1800630df  mov     ebx, edx
0x1800630e1  mov     rsi, rcx
0x1800630e4  mov     r9d, 1; unsigned __int16
0x1800630ea  mov     r8d, 277h; unsigned __int16
0x1800630f0  lea     rdx, aCrefsvolumeRem; "CReFsVolume::RemoveFile"
0x1800630f7  lea     rcx, [rbp+var_40]; this
0x1800630fb  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180063100  nop
0x180063101  mov     [rbp+arg_10], 0
0x180063109  mov     [rbp+arg_8], ebx
0x18006310c  mov     eax, 27Bh
0x180063111  test    ebx, ebx
0x180063113  jnz     short loc_180063126
0x180063115  mov     ebx, 80070057h
0x18006311a  mov     [rbp+var_40], ebx
0x18006311d  mov     [rbp+var_3A], ax
0x180063121  jmp     loc_1800631C3
0x180063126  mov     [rbp+var_40], 0
0x18006312d  mov     [rbp+var_3C], ax
0x180063131  lea     r8, [rbp+arg_10]
0x180063135  lea     rdx, [rbp+arg_8]
0x180063139  mov     rcx, [rsi+438h]
0x180063140  call    ?GetElement@?$CBulkAllocator@VCReFsFile@@@@QEAAJPEAKPEAPEAVCReFsFile@@@Z; CBulkAllocator<CReFsFile>::GetElement(ulong *,CReFsFile * *)
0x180063145  mov     ebx, eax
0x180063147  mov     [rbp+var_40], eax
0x18006314a  test    eax, eax
0x18006314c  mov     eax, 27Dh
0x180063151  js      short loc_18006311D
0x180063153  mov     [rbp+var_3C], ax
0x180063157  mov     rdi, [rbp+arg_10]
0x18006315b  test    rdi, rdi
0x18006315e  jz      short loc_180063182
0x180063160  cmp     dword ptr [rdi], 0
0x180063163  jz      short loc_180063182
0x180063165  mov     rdx, rdi; unsigned int *
0x180063168  mov     rcx, rsi; this
0x18006316b  call    ?_FreeExtents@CVolume@@IEAAJPEAK@Z; CVolume::_FreeExtents(ulong *)
0x180063170  mov     ebx, eax
0x180063172  mov     [rbp+var_40], eax
0x180063175  test    eax, eax
0x180063177  mov     eax, 281h
0x18006317c  js      short loc_18006311D
0x18006317e  mov     [rbp+var_3C], ax
0x180063182  mov     rcx, [rdi+10h]; pv
0x180063186  call    cs:__imp_CoTaskMemFree
0x18006318c  mov     qword ptr [rdi+10h], 0
0x180063194  lea     rdx, [rbp+arg_8]
0x180063198  mov     rcx, [rsi+438h]
0x18006319f  call    ?Free@?$CBulkAllocator@U_CExtent@@@@QEAAJPEAK@Z; CBulkAllocator<_CExtent>::Free(ulong *)
0x1800631a4  mov     ebx, eax
0x1800631a6  mov     [rbp+var_40], eax
0x1800631a9  test    eax, eax
0x1800631ab  mov     eax, 288h
0x1800631b0  js      loc_18006311D
0x1800631b6  mov     [rbp+var_3C], ax
0x1800631ba  mov     [rbp+var_40], 0
0x1800631c1  xor     ebx, ebx
0x1800631c3  lea     rcx, [rbp+var_40]; this
0x1800631c7  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800631cc  mov     eax, ebx
0x1800631ce  mov     rbx, [rsp+60h+arg_0]
0x1800631d6  add     rsp, 60h
0x1800631da  pop     rdi
0x1800631db  pop     rsi
0x1800631dc  pop     rbp
0x1800631dd  retn
```
