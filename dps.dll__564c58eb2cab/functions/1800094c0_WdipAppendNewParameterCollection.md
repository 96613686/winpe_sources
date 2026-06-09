# WdipAppendNewParameterCollection

- ea: `0x1800094c0`
- end: `0x180009657`
- name: `WdipAppendNewParameterCollection`
- size: `407`
- prototype: `__int64 __fastcall(__int64, __int64, _OWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002510`
- `0x18000b6d8`
- `0x18000c21c`

## callees

- `0x180009090`
- `0x18000934c`
- `0x1800094c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800095af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800095cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800095ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800095af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800095cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800095ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095e0`

## string_xrefs

- `0x1800094f4`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x180009617`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`

## pseudocode

```c
__int64 __fastcall WdipAppendNewParameterCollection(__int64 a1, __int64 a2, _OWORD *a3)
{
  int v6; // r8d
  __int64 v8; // rbp
  int Args; // r15d
  __int64 v10; // rbx
  _OWORD *v11; // rcx
  _QWORD *v12; // rdi
  _QWORD *v13; // r14
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  void *v16; // rbx
  HANDLE v17; // rax
  _QWORD *v18; // rbx
  HANDLE v19; // rax

  if ( !a1 )
  {
    v6 = 701;
LABEL_3:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipAppendNewParameterCollection",
      v6,
      (int)L"Error = %d",
      87);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    v6 = 702;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v6 = 703;
    goto LABEL_3;
  }
  v8 = 0;
  for ( Args = 0; (unsigned int)v8 < *(_DWORD *)(a2 + 4); v8 = (unsigned int)(v8 + 1) )
  {
    v10 = 8 * v8;
    v11 = *(_OWORD **)(8 * v8 + *(_QWORD *)(a2 + 8));
    if ( v11 )
    {
      *v11 = *a3;
      Args = WdipAddParameterToCollection(a1, *(_QWORD *)(v10 + *(_QWORD *)(a2 + 8)));
      if ( Args < 0 )
      {
        v12 = (_QWORD *)(v10 + *(_QWORD *)(a2 + 8));
        if ( v12 )
        {
          v13 = (_QWORD *)*v12;
          if ( *v12 )
          {
            v14 = (void *)v13[6];
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v14);
            v16 = (void *)v13[7];
            v13[6] = 0;
            v17 = GetProcessHeap();
            HeapFree(v17, 0, v16);
            v13[7] = 0;
          }
          v18 = (_QWORD *)*v12;
          v19 = GetProcessHeap();
          HeapFree(v19, 0, v18);
          *v12 = 0;
        }
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
          (int)L"WdipAppendNewParameterCollection",
          719,
          (int)L"Error = %d",
          Args);
        Args = 0;
      }
    }
  }
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x1800094c0  push    rsi
0x1800094c2  push    r12
0x1800094c4  push    r13
0x1800094c6  sub     rsp, 40h
0x1800094ca  mov     r12, r8
0x1800094cd  mov     rsi, rdx
0x1800094d0  mov     r13, rcx
0x1800094d3  test    rcx, rcx
0x1800094d6  jnz     short loc_18000950F
0x1800094d8  mov     r8d, 2BDh; int
0x1800094de  lea     r9, aErrorD; "Error = %d"
0x1800094e5  mov     dword ptr [rsp+58h+Args], 57h ; 'W'; Args
0x1800094ed  lea     rdx, aWdipappendnewp; "WdipAppendNewParameterCollection"
0x1800094f4  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800094fb  call    WdipTraceError
0x180009500  mov     eax, 80070057h
0x180009505  add     rsp, 40h
0x180009509  pop     r13
0x18000950b  pop     r12
0x18000950d  pop     rsi
0x18000950e  retn
0x18000950f  test    rsi, rsi
0x180009512  jnz     short loc_18000951C
0x180009514  mov     r8d, 2BEh
0x18000951a  jmp     short loc_1800094DE
0x18000951c  test    r12, r12
0x18000951f  jnz     short loc_180009529
0x180009521  mov     r8d, 2BFh
0x180009527  jmp     short loc_1800094DE
0x180009529  mov     [rsp+58h+arg_8], rbp
0x18000952e  xor     ebp, ebp
0x180009530  mov     [rsp+58h+var_28], r15
0x180009535  xor     r15d, r15d
0x180009538  cmp     [rdx+4], ebp
0x18000953b  jbe     loc_180009640
0x180009541  mov     [rsp+58h+arg_0], rbx
0x180009546  mov     [rsp+58h+arg_10], rdi
0x18000954b  mov     [rsp+58h+var_20], r14
0x180009550  mov     rax, [rsi+8]
0x180009554  lea     rbx, ds:0[rbp*8]
0x18000955c  mov     rcx, [rbx+rax]
0x180009560  test    rcx, rcx
0x180009563  jz      loc_180009626
0x180009569  movups  xmm0, xmmword ptr [r12]
0x18000956e  movups  xmmword ptr [rcx], xmm0
0x180009571  mov     rdx, [rsi+8]
0x180009575  mov     rcx, r13
0x180009578  mov     rdx, [rbx+rdx]
0x18000957c  call    WdipAddParameterToCollection
0x180009581  mov     r15d, eax
0x180009584  test    eax, eax
0x180009586  jns     loc_180009626
0x18000958c  mov     rdi, [rsi+8]
0x180009590  add     rdi, rbx
0x180009593  jz      short loc_1800095FB
0x180009595  mov     r14, [rdi]
0x180009598  test    r14, r14
0x18000959b  jz      short loc_1800095DD
0x18000959d  mov     rbx, [r14+30h]
0x1800095a1  call    cs:__imp_GetProcessHeap
0x1800095a7  mov     r8, rbx; lpMem
0x1800095aa  xor     edx, edx; dwFlags
0x1800095ac  mov     rcx, rax; hHeap
0x1800095af  call    cs:__imp_HeapFree
0x1800095b5  mov     rbx, [r14+38h]
0x1800095b9  mov     qword ptr [r14+30h], 0
0x1800095c1  call    cs:__imp_GetProcessHeap
0x1800095c7  mov     r8, rbx; lpMem
0x1800095ca  xor     edx, edx; dwFlags
0x1800095cc  mov     rcx, rax; hHeap
0x1800095cf  call    cs:__imp_HeapFree
0x1800095d5  mov     qword ptr [r14+38h], 0
0x1800095dd  mov     rbx, [rdi]
0x1800095e0  call    cs:__imp_GetProcessHeap
0x1800095e6  mov     r8, rbx; lpMem
0x1800095e9  xor     edx, edx; dwFlags
0x1800095eb  mov     rcx, rax; hHeap
0x1800095ee  call    cs:__imp_HeapFree
0x1800095f4  mov     qword ptr [rdi], 0
0x1800095fb  movzx   eax, r15w
0x1800095ff  lea     r9, aErrorD; "Error = %d"
0x180009606  mov     r8d, 2CFh; int
0x18000960c  mov     dword ptr [rsp+58h+Args], eax; Args
0x180009610  lea     rdx, aWdipappendnewp; "WdipAppendNewParameterCollection"
0x180009617  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000961e  call    WdipTraceError
0x180009623  xor     r15d, r15d
0x180009626  inc     ebp
0x180009628  cmp     ebp, [rsi+4]
0x18000962b  jb      loc_180009550
0x180009631  mov     r14, [rsp+58h+var_20]
0x180009636  mov     rdi, [rsp+58h+arg_10]
0x18000963b  mov     rbx, [rsp+58h+arg_0]
0x180009640  mov     rbp, [rsp+58h+arg_8]
0x180009645  mov     eax, r15d
0x180009648  mov     r15, [rsp+58h+var_28]
0x18000964d  add     rsp, 40h
0x180009651  pop     r13
0x180009653  pop     r12
0x180009655  pop     rsi
0x180009656  retn
```
