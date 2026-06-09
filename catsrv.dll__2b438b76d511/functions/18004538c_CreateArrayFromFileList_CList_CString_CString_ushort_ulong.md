# CreateArrayFromFileList(CList<CString,CString &> &,ushort * * *,ulong *)

- ea: `0x18004538c`
- end: `0x1800454b3`
- name: `?CreateArrayFromFileList@@YAJAEAV?$CList@VCString@@AEAV1@@@PEAPEAPEAGPEAK@Z`
- size: `295`
- prototype: `__int64 __fastcall(__int64, LPVOID *, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004859c`

## callees

- `0x18000a01c`
- `0x18001a6c8`
- `0x18004538c`
- `0x18005551a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045476`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045495`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045476`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180045495`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800453cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045416`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800453cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045416`

## pseudocode

```c
__int64 __fastcall CreateArrayFromFileList(__int64 a1, LPVOID *a2, _DWORD *a3)
{
  __int64 v5; // r12
  __int64 **v7; // r14
  void *v8; // rax
  int v9; // ebx
  __int64 v10; // rsi
  __int64 *v11; // rbp
  unsigned __int64 v12; // rbx
  unsigned __int16 *v13; // rcx
  __int64 v14; // rbp
  void *v15; // rcx

  *a2 = 0;
  *a3 = 0;
  v5 = *(unsigned int *)(a1 + 24);
  if ( !(_DWORD)v5 )
    return 0;
  v7 = *(__int64 ***)(a1 + 8);
  v8 = CoTaskMemAlloc(8 * v5);
  *a2 = v8;
  if ( !v8 )
    return 2147942414LL;
  v9 = 0;
  v10 = 0;
  memset_0(v8, 0, 8 * v5);
  while ( v7 )
  {
    if ( (unsigned int)v10 >= (unsigned int)v5 )
    {
      v9 = -2147467259;
      goto LABEL_14;
    }
    v11 = *v7;
    v12 = (int)(safe_lstrlenW((const unsigned __int16 *)v7[2]) + 2);
    *((_QWORD *)*a2 + v10) = CoTaskMemAlloc(2 * v12);
    v13 = (unsigned __int16 *)*((_QWORD *)*a2 + v10);
    if ( !v13 )
    {
      v9 = -2147024882;
      goto LABEL_14;
    }
    v9 = StringCchCopyW(v13, v12, (const unsigned __int16 *)v7[2]);
    if ( v9 < 0 )
      goto LABEL_14;
    v7 = (__int64 **)v11;
    v10 = (unsigned int)(v10 + 1);
  }
  *a3 = v10;
  if ( !v9 )
    return (unsigned int)v9;
LABEL_14:
  v14 = 0;
  for ( *a3 = 0; (unsigned int)v14 < (unsigned int)v10; v14 = (unsigned int)(v14 + 1) )
  {
    v15 = (void *)*((_QWORD *)*a2 + v14);
    if ( v15 )
    {
      CoTaskMemFree(v15);
      *((_QWORD *)*a2 + v14) = 0;
    }
  }
  if ( *a2 )
  {
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004538c  push    rbx
0x18004538e  push    rbp
0x18004538f  push    rsi
0x180045390  push    rdi
0x180045391  push    r12
0x180045393  push    r14
0x180045395  push    r15
0x180045397  sub     rsp, 20h
0x18004539b  mov     qword ptr [rdx], 0
0x1800453a2  mov     r15, r8
0x1800453a5  mov     dword ptr [r8], 0
0x1800453ac  mov     rdi, rdx
0x1800453af  mov     r12d, [rcx+18h]
0x1800453b3  test    r12d, r12d
0x1800453b6  jnz     short loc_1800453BF
0x1800453b8  xor     eax, eax
0x1800453ba  jmp     loc_1800454A4
0x1800453bf  mov     r14, [rcx+8]
0x1800453c3  mov     rbp, r12
0x1800453c6  shl     rbp, 3
0x1800453ca  mov     rcx, rbp; cb
0x1800453cd  call    cs:__imp_CoTaskMemAlloc
0x1800453d3  mov     [rdi], rax
0x1800453d6  test    rax, rax
0x1800453d9  jnz     short loc_1800453E5
0x1800453db  mov     eax, 8007000Eh
0x1800453e0  jmp     loc_1800454A4
0x1800453e5  xor     ebx, ebx
0x1800453e7  xor     esi, esi
0x1800453e9  mov     r8, rbp; Size
0x1800453ec  xor     edx, edx; Val
0x1800453ee  mov     rcx, rax; void *
0x1800453f1  call    memset_0
0x1800453f6  test    r14, r14
0x1800453f9  jz      short loc_180045456
0x1800453fb  cmp     esi, r12d
0x1800453fe  jnb     short loc_18004544F
0x180045400  mov     rcx, [r14+10h]; unsigned __int16 *
0x180045404  mov     rbp, [r14]
0x180045407  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18004540c  add     eax, 2
0x18004540f  movsxd  rbx, eax
0x180045412  lea     rcx, [rbx+rbx]; cb
0x180045416  call    cs:__imp_CoTaskMemAlloc
0x18004541c  mov     rcx, [rdi]
0x18004541f  mov     [rcx+rsi*8], rax
0x180045423  mov     rax, [rdi]
0x180045426  mov     rcx, [rax+rsi*8]; unsigned __int16 *
0x18004542a  test    rcx, rcx
0x18004542d  jz      short loc_180045448
0x18004542f  mov     r8, [r14+10h]; unsigned __int16 *
0x180045433  mov     rdx, rbx; unsigned __int64
0x180045436  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004543b  mov     ebx, eax
0x18004543d  test    eax, eax
0x18004543f  js      short loc_18004545D
0x180045441  mov     r14, rbp
0x180045444  inc     esi
0x180045446  jmp     short loc_1800453F6
0x180045448  mov     ebx, 8007000Eh
0x18004544d  jmp     short loc_18004545D
0x18004544f  mov     ebx, 80004005h
0x180045454  jmp     short loc_18004545D
0x180045456  mov     [r15], esi
0x180045459  test    ebx, ebx
0x18004545b  jz      short loc_1800454A2
0x18004545d  xor     ebp, ebp
0x18004545f  mov     dword ptr [r15], 0
0x180045466  test    esi, esi
0x180045468  jz      short loc_18004548D
0x18004546a  mov     rax, [rdi]
0x18004546d  mov     rcx, [rax+rbp*8]; pv
0x180045471  test    rcx, rcx
0x180045474  jz      short loc_180045487
0x180045476  call    cs:__imp_CoTaskMemFree
0x18004547c  mov     rax, [rdi]
0x18004547f  mov     qword ptr [rax+rbp*8], 0
0x180045487  inc     ebp
0x180045489  cmp     ebp, esi
0x18004548b  jb      short loc_18004546A
0x18004548d  mov     rcx, [rdi]; pv
0x180045490  test    rcx, rcx
0x180045493  jz      short loc_1800454A2
0x180045495  call    cs:__imp_CoTaskMemFree
0x18004549b  mov     qword ptr [rdi], 0
0x1800454a2  mov     eax, ebx
0x1800454a4  add     rsp, 20h
0x1800454a8  pop     r15
0x1800454aa  pop     r14
0x1800454ac  pop     r12
0x1800454ae  pop     rdi
0x1800454af  pop     rsi
0x1800454b0  pop     rbp
0x1800454b1  pop     rbx
0x1800454b2  retn
```
