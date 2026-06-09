# CFatVolume::RemoveFile(ulong)

- ea: `0x180008980`
- end: `0x180008ae1`
- name: `?RemoveFile@CFatVolume@@UEAAJK@Z`
- size: `353`
- prototype: `__int64 __fastcall(CFatVolume *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x180006bf8`
- `0x180008980`
- `0x180008af0`
- `0x18000ad50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008a62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008a62`

## string_xrefs

- `0x18000899d`: `CFatVolume::RemoveFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFatVolume::RemoveFile(CFatVolume *this, unsigned int a2)
{
  __int16 v4; // ax
  __int64 v5; // rdx
  unsigned int v6; // r8d
  _QWORD *v7; // rax
  __int64 v8; // rdi
  bool v9; // zf
  __int64 v10; // rdi
  int v11; // ebx
  int v13; // eax
  int v14; // [rsp+20h] [rbp-48h] BYREF
  __int16 v15; // [rsp+24h] [rbp-44h]
  __int16 v16; // [rsp+26h] [rbp-42h]
  unsigned int v17; // [rsp+98h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v14, "CFatVolume::RemoveFile", 631, 1);
  v17 = a2;
  v4 = 635;
  if ( !a2 )
  {
    v11 = -2147024809;
    v14 = -2147024809;
    goto LABEL_11;
  }
  v14 = 0;
  v15 = 635;
  v5 = *((_QWORD *)this + 135);
  if ( !*(_DWORD *)(v5 + 28) )
  {
    v13 = -2147467259;
    v14 = -2147467259;
LABEL_16:
    v16 = 637;
    v11 = v13;
    goto LABEL_12;
  }
  if ( (a2 & 0xF0000000) != *(_DWORD *)(v5 + 28)
    || (v6 = (unsigned __int16)a2 != 0 ? (unsigned __int16)a2 - 1 : 0,
        (v7 = *(_QWORD **)(*(_QWORD *)(v5 + 8) + 8LL * (HIWORD(a2) & 0xFFF))) == 0)
    || v6 >= *(_DWORD *)(v5 + 20) )
  {
    v13 = -2147024809;
    v14 = -2147024809;
    goto LABEL_16;
  }
  v8 = *(_QWORD *)(v5 + 32) * v6;
  v9 = *v7 + v8 == 0;
  v10 = *v7 + v8;
  v14 = 0;
  v15 = 637;
  if ( v9 || !*(_DWORD *)v10 )
  {
LABEL_10:
    CoTaskMemFree(*(LPVOID *)(v10 + 16));
    *(_QWORD *)(v10 + 16) = 0;
    v11 = CBulkAllocator<CFatFile>::Free(*((_QWORD *)this + 135), &v17);
    v14 = v11;
    v4 = 648;
    if ( v11 >= 0 )
    {
      v15 = 648;
      v14 = 0;
      v11 = 0;
      goto LABEL_12;
    }
    goto LABEL_11;
  }
  v11 = CVolume::_FreeExtents(this, (unsigned int *)v10);
  v14 = v11;
  v4 = 641;
  if ( v11 >= 0 )
  {
    v15 = 641;
    goto LABEL_10;
  }
LABEL_11:
  v16 = v4;
LABEL_12:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v14);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180008980  push    rbp
0x180008982  push    rbx
0x180008983  push    rsi
0x180008984  push    rdi
0x180008985  mov     rbp, rsp
0x180008988  sub     rsp, 68h
0x18000898c  mov     ebx, edx
0x18000898e  mov     rsi, rcx
0x180008991  mov     r9d, 1; unsigned __int16
0x180008997  mov     r8d, 277h; unsigned __int16
0x18000899d  lea     rdx, aCfatvolumeRemo; "CFatVolume::RemoveFile"
0x1800089a4  lea     rcx, [rbp+var_48]; this
0x1800089a8  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800089ad  nop
0x1800089ae  mov     [rbp+arg_8], ebx
0x1800089b1  mov     eax, 27Bh
0x1800089b6  test    ebx, ebx
0x1800089b8  jz      loc_180008AA6
0x1800089be  mov     [rbp+var_48], 0
0x1800089c5  mov     [rbp+var_44], ax
0x1800089c9  mov     rdx, [rsi+438h]
0x1800089d0  cmp     dword ptr [rdx+1Ch], 0
0x1800089d4  jbe     loc_180008AB0
0x1800089da  mov     eax, ebx
0x1800089dc  and     eax, 0F0000000h
0x1800089e1  cmp     eax, [rdx+1Ch]
0x1800089e4  jnz     loc_180008ABA
0x1800089ea  movzx   eax, bx
0x1800089ed  lea     ecx, [rax-1]
0x1800089f0  neg     eax
0x1800089f2  sbb     r8d, r8d
0x1800089f5  and     r8d, ecx
0x1800089f8  mov     ecx, ebx
0x1800089fa  shr     rcx, 10h
0x1800089fe  and     ecx, 0FFFh
0x180008a04  mov     rax, [rdx+8]
0x180008a08  mov     rax, [rax+rcx*8]
0x180008a0c  test    rax, rax
0x180008a0f  jz      loc_180008ABA
0x180008a15  cmp     r8d, [rdx+14h]
0x180008a19  jnb     loc_180008ABA
0x180008a1f  mov     edi, r8d
0x180008a22  imul    rdi, [rdx+20h]
0x180008a27  add     rdi, [rax]
0x180008a2a  mov     [rbp+var_48], 0
0x180008a31  mov     ecx, 27Dh
0x180008a36  mov     [rbp+var_44], cx
0x180008a3a  jz      short loc_180008A5E
0x180008a3c  cmp     dword ptr [rdi], 0
0x180008a3f  jz      short loc_180008A5E
0x180008a41  mov     rdx, rdi; unsigned int *
0x180008a44  mov     rcx, rsi; this
0x180008a47  call    ?_FreeExtents@CVolume@@IEAAJPEAK@Z; CVolume::_FreeExtents(ulong *)
0x180008a4c  mov     ebx, eax
0x180008a4e  mov     [rbp+var_48], eax
0x180008a51  test    eax, eax
0x180008a53  mov     eax, 281h
0x180008a58  js      short loc_180008A8E
0x180008a5a  mov     [rbp+var_44], ax
0x180008a5e  mov     rcx, [rdi+10h]; pv
0x180008a62  call    cs:__imp_CoTaskMemFree
0x180008a68  mov     qword ptr [rdi+10h], 0
0x180008a70  lea     rdx, [rbp+arg_8]
0x180008a74  mov     rcx, [rsi+438h]
0x180008a7b  call    ?Free@?$CBulkAllocator@VCFatFile@@@@QEAAJPEAK@Z; CBulkAllocator<CFatFile>::Free(ulong *)
0x180008a80  mov     ebx, eax
0x180008a82  mov     [rbp+var_48], eax
0x180008a85  test    eax, eax
0x180008a87  mov     eax, 288h
0x180008a8c  jns     short loc_180008AD1
0x180008a8e  mov     [rbp+var_42], ax
0x180008a92  lea     rcx, [rbp+var_48]; this
0x180008a96  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180008a9b  mov     eax, ebx
0x180008a9d  add     rsp, 68h
0x180008aa1  pop     rdi
0x180008aa2  pop     rsi
0x180008aa3  pop     rbx
0x180008aa4  pop     rbp
0x180008aa5  retn
0x180008aa6  mov     ebx, 80070057h
0x180008aab  mov     [rbp+var_48], ebx
0x180008aae  jmp     short loc_180008A8E
0x180008ab0  mov     eax, 80004005h
0x180008ab5  mov     [rbp+var_48], eax
0x180008ab8  jmp     short loc_180008AC4
0x180008aba  mov     ebx, 80070057h
0x180008abf  mov     eax, ebx
0x180008ac1  mov     [rbp+var_48], ebx
0x180008ac4  mov     ecx, 27Dh
0x180008ac9  mov     [rbp+var_42], cx
0x180008acd  mov     ebx, eax
0x180008acf  jmp     short loc_180008A92
0x180008ad1  mov     [rbp+var_44], ax
0x180008ad5  mov     [rbp+var_48], 0
0x180008adc  xor     ebx, ebx
0x180008ade  jmp     short loc_180008A92
```
