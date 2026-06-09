# CDefragEngine::_DeleteVolumeStatusList(__MIDL___MIDL_itf_dfengine_0000_0000_0007 *,ulong)

- ea: `0x18001ea0c`
- end: `0x18001eb39`
- name: `?_DeleteVolumeStatusList@CDefragEngine@@AEAAJPEAU__MIDL___MIDL_itf_dfengine_0000_0000_0007@@K@Z`
- size: `301`
- prototype: `__int64 __fastcall(CDefragEngine *this, LPVOID *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c8b0`
- `0x18001d914`
- `0x180045650`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001ea0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ea74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ea86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ea9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eab3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eacb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eaf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eb1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ea74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ea86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ea9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eab3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eacb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eaf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eb1a`

## string_xrefs

- `0x18001ea27`: `CDefragEngine::_DeleteVolumeStatusList`

## pseudocode

```c
__int64 __fastcall CDefragEngine::_DeleteVolumeStatusList(CDefragEngine *this, LPVOID *a2, unsigned int a3)
{
  unsigned int v5; // ebx
  LPVOID *v6; // rbx
  unsigned int i; // ebp
  int v9; // [rsp+20h] [rbp-68h] BYREF
  __int16 v10; // [rsp+24h] [rbp-64h]
  __int16 v11; // [rsp+26h] [rbp-62h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "CDefragEngine::_DeleteVolumeStatusList", 3610, 1);
  if ( a2 )
  {
    v9 = 0;
    v10 = 3614;
    v6 = a2;
    for ( i = 0; i < a3; ++i )
    {
      CoTaskMemFree(v6[14]);
      v6[14] = 0;
      CoTaskMemFree(v6[15]);
      v6[15] = 0;
      CoTaskMemFree(v6[16]);
      v6[16] = 0;
      CoTaskMemFree(v6[18]);
      v6[18] = 0;
      CoTaskMemFree(v6[17]);
      v6[17] = 0;
      CoTaskMemFree(v6[13]);
      v6[13] = 0;
      CoTaskMemFree(v6[20]);
      v6[20] = 0;
      v6 += 26;
    }
    CoTaskMemFree(a2);
    v5 = v9;
  }
  else
  {
    v5 = -2147024809;
    v9 = -2147024809;
    v11 = 3614;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return v5;
}

```

## disassembly

```asm
0x18001ea0c  push    rbx
0x18001ea0e  push    rbp
0x18001ea0f  push    rsi
0x18001ea10  push    rdi
0x18001ea11  sub     rsp, 68h
0x18001ea15  mov     esi, r8d
0x18001ea18  mov     rdi, rdx
0x18001ea1b  mov     r9d, 1; unsigned __int16
0x18001ea21  mov     r8d, 0E1Ah; unsigned __int16
0x18001ea27  lea     rdx, aCdefragengineD_1; "CDefragEngine::_DeleteVolumeStatusList"
0x18001ea2e  lea     rcx, [rsp+88h+var_68]; this
0x18001ea33  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001ea38  nop
0x18001ea39  mov     eax, 0E1Eh
0x18001ea3e  test    rdi, rdi
0x18001ea41  jnz     short loc_18001EA56
0x18001ea43  mov     ebx, 80070057h
0x18001ea48  mov     [rsp+88h+var_68], ebx
0x18001ea4c  mov     [rsp+88h+var_62], ax
0x18001ea51  jmp     loc_18001EB24
0x18001ea56  mov     [rsp+88h+var_68], 0
0x18001ea5e  mov     [rsp+88h+var_64], ax
0x18001ea63  mov     rbx, rdi
0x18001ea66  xor     ebp, ebp
0x18001ea68  test    esi, esi
0x18001ea6a  jz      loc_18001EB17
0x18001ea70  mov     rcx, [rbx+70h]; pv
0x18001ea74  call    cs:__imp_CoTaskMemFree
0x18001ea7a  mov     qword ptr [rbx+70h], 0
0x18001ea82  mov     rcx, [rbx+78h]; pv
0x18001ea86  call    cs:__imp_CoTaskMemFree
0x18001ea8c  mov     qword ptr [rbx+78h], 0
0x18001ea94  mov     rcx, [rbx+80h]; pv
0x18001ea9b  call    cs:__imp_CoTaskMemFree
0x18001eaa1  mov     qword ptr [rbx+80h], 0
0x18001eaac  mov     rcx, [rbx+90h]; pv
0x18001eab3  call    cs:__imp_CoTaskMemFree
0x18001eab9  mov     qword ptr [rbx+90h], 0
0x18001eac4  mov     rcx, [rbx+88h]; pv
0x18001eacb  call    cs:__imp_CoTaskMemFree
0x18001ead1  mov     qword ptr [rbx+88h], 0
0x18001eadc  mov     rcx, [rbx+68h]; pv
0x18001eae0  call    cs:__imp_CoTaskMemFree
0x18001eae6  mov     qword ptr [rbx+68h], 0
0x18001eaee  mov     rcx, [rbx+0A0h]; pv
0x18001eaf5  call    cs:__imp_CoTaskMemFree
0x18001eafb  mov     qword ptr [rbx+0A0h], 0
0x18001eb06  lea     rbx, [rbx+0D0h]
0x18001eb0d  inc     ebp
0x18001eb0f  cmp     ebp, esi
0x18001eb11  jb      loc_18001EA70
0x18001eb17  mov     rcx, rdi; pv
0x18001eb1a  call    cs:__imp_CoTaskMemFree
0x18001eb20  mov     ebx, [rsp+88h+var_68]
0x18001eb24  lea     rcx, [rsp+88h+var_68]; this
0x18001eb29  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001eb2e  mov     eax, ebx
0x18001eb30  add     rsp, 68h
0x18001eb34  pop     rdi
0x18001eb35  pop     rsi
0x18001eb36  pop     rbp
0x18001eb37  pop     rbx
0x18001eb38  retn
```
