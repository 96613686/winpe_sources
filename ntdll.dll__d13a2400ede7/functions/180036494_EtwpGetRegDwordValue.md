# EtwpGetRegDwordValue

- ea: `0x180036494`
- end: `0x180036675`
- name: `EtwpGetRegDwordValue`
- size: `481`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180034bd0`

## callees

- `0x18001861c`
- `0x18001b984`
- `0x180036494`
- `0x1801010ac`
- `0x18012d320`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015edc0`

## string_xrefs

- `0x180036501`: `\Registry\Machine\System\CurrentControlSet\Control`

## pseudocode

```c
__int64 __fastcall EtwpGetRegDwordValue(__int64 a1, __int64 a2, _DWORD *a3)
{
  wchar_t *Heap_0; // rsi
  size_t v5; // rax
  int v6; // ebx
  size_t v7; // rdx
  __int64 v8; // rdi
  size_t *v9; // r8
  const wchar_t *v10; // r9
  size_t v12; // rax
  size_t v13; // [rsp+20h] [rbp-60h]
  __int128 v14; // [rsp+30h] [rbp-50h] BYREF
  __int128 v15; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v16[48]; // [rsp+50h] [rbp-30h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp+30h] BYREF
  int v18; // [rsp+B8h] [rbp+38h] BYREF
  int v19; // [rsp+BCh] [rbp+3Ch]

  v19 = HIDWORD(a2);
  v18 = 0;
  Handle = (HANDLE)-1LL;
  memset(v16, 0, 44);
  v14 = 0;
  Heap_0 = (wchar_t *)RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, 4096);
  if ( !Heap_0 )
    return 3221225495LL;
  *(_QWORD *)&v14 = 0;
  *((_QWORD *)&v14 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control";
  v5 = 2 * wcslen(L"\\Registry\\Machine\\System\\CurrentControlSet\\Control");
  *(_OWORD *)v16 = 0x30u;
  *(_QWORD *)&v16[24] = 64;
  if ( v5 >= 0xFFFE )
    LOWORD(v5) = -4;
  LOWORD(v14) = v5;
  WORD1(v14) = v5 + 2;
  *(_QWORD *)&v16[16] = &v14;
  *(_OWORD *)&v16[32] = 0;
  v6 = NtOpenKey(&Handle, 131097, v16);
  if ( v6 >= 0 )
  {
    v8 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, 0, 16);
    if ( v8 )
    {
      v15 = 0;
      StringCopyWorkerW(Heap_0, v7, v9, v10, v13);
      *(_QWORD *)&v15 = 0;
      *((_QWORD *)&v15 + 1) = Heap_0;
      v12 = 2 * wcslen(Heap_0);
      if ( v12 >= 0xFFFE )
        LOWORD(v12) = -4;
      LOWORD(v15) = v12;
      WORD1(v15) = v12 + 2;
      v6 = NtQueryValueKey(Handle, &v15, 2, v8, 16, &v18);
      if ( v6 >= 0 )
        *a3 = *(_DWORD *)(v8 + 12);
      RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v8);
    }
    else
    {
      v6 = -1073741801;
    }
    NtClose(Handle);
  }
  RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, Heap_0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180036494  mov     [rsp-28h+arg_10], rbx
0x180036499  mov     [rsp-28h+arg_8], rdx
0x18003649e  mov     [rsp-28h+Handle], rcx
0x1800364a3  push    rbp
0x1800364a4  push    rsi
0x1800364a5  push    rdi
0x1800364a6  push    r12
0x1800364a8  push    r14
0x1800364aa  mov     rbp, rsp
0x1800364ad  sub     rsp, 80h
0x1800364b4  xorps   xmm0, xmm0
0x1800364b7  mov     dword ptr [rbp+arg_8], 0
0x1800364be  movups  [rbp+var_20], xmm0
0x1800364c2  mov     [rbp+Handle], 0FFFFFFFFFFFFFFFFh
0x1800364ca  mov     r14, r8
0x1800364cd  movups  [rbp+var_20+0Ch], xmm0
0x1800364d1  xor     eax, eax
0x1800364d3  xor     edx, edx
0x1800364d5  movups  [rbp+var_30], xmm0
0x1800364d9  mov     r8d, 1000h
0x1800364df  movups  [rbp+var_50], xmm0
0x1800364e3  mov     rcx, gs:60h
0x1800364ec  mov     rcx, [rcx+30h]
0x1800364f0  call    RtlAllocateHeap_0
0x1800364f5  mov     rsi, rax
0x1800364f8  test    rax, rax
0x1800364fb  jz      loc_180036663
0x180036501  lea     rcx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x180036508  mov     qword ptr [rbp+var_50], 0
0x180036510  mov     qword ptr [rbp+var_50+8], rcx
0x180036514  call    wcslen
0x180036519  add     rax, rax
0x18003651c  mov     qword ptr [rbp+var_30], 30h ; '0'
0x180036524  cmp     rax, 0FFFEh
0x18003652a  mov     qword ptr [rbp+var_20+8], 40h ; '@'
0x180036532  mov     ecx, 0FFFCh
0x180036537  mov     qword ptr [rbp+var_30+8], 0
0x18003653f  cmovnb  rax, rcx
0x180036543  lea     r8, [rbp+var_30]
0x180036547  mov     word ptr [rbp+var_50], ax
0x18003654b  lea     rcx, [rbp+Handle]
0x18003654f  xorps   xmm0, xmm0
0x180036552  mov     r12d, 2
0x180036558  add     ax, r12w
0x18003655c  mov     edx, 20019h
0x180036561  mov     word ptr [rbp+var_50+2], ax
0x180036565  lea     rax, [rbp+var_50]
0x180036569  mov     qword ptr [rbp+var_20], rax
0x18003656d  movdqu  [rbp+var_10], xmm0
0x180036572  call    NtOpenKey
0x180036577  mov     ebx, eax
0x180036579  test    eax, eax
0x18003657b  js      short loc_1800365AF
0x18003657d  mov     rcx, gs:60h
0x180036586  lea     ebx, [r12+0Eh]
0x18003658b  mov     r8d, ebx
0x18003658e  xor     edx, edx
0x180036590  mov     rcx, [rcx+30h]
0x180036594  call    RtlAllocateHeap_0
0x180036599  mov     rdi, rax
0x18003659c  test    rax, rax
0x18003659f  jnz     short loc_1800365E0
0x1800365a1  mov     ebx, 0C0000017h
0x1800365a6  mov     rcx, [rbp+Handle]; Handle
0x1800365aa  call    NtClose
0x1800365af  mov     rcx, gs:60h
0x1800365b8  mov     r8, rsi
0x1800365bb  xor     edx, edx
0x1800365bd  mov     rcx, [rcx+30h]
0x1800365c1  call    RtlFreeHeap_0
0x1800365c6  mov     eax, ebx
0x1800365c8  mov     rbx, [rsp+80h+arg_10]
0x1800365d0  add     rsp, 80h
0x1800365d7  pop     r14
0x1800365d9  pop     r12
0x1800365db  pop     rdi
0x1800365dc  pop     rsi
0x1800365dd  pop     rbp
0x1800365de  retn
0x1800365e0  xorps   xmm0, xmm0
0x1800365e3  mov     rcx, rsi; pszDest
0x1800365e6  movups  [rbp+var_40], xmm0
0x1800365ea  call    StringCopyWorkerW
0x1800365ef  mov     rcx, rsi; String
0x1800365f2  mov     qword ptr [rbp+var_40], 0
0x1800365fa  mov     qword ptr [rbp+var_40+8], rsi
0x1800365fe  call    wcslen
0x180036603  add     rax, rax
0x180036606  lea     rdx, [rbp+var_40]
0x18003660a  cmp     rax, 0FFFEh
0x180036610  mov     ecx, 0FFFCh
0x180036615  mov     r9, rdi
0x180036618  mov     r8d, r12d
0x18003661b  cmovnb  rax, rcx
0x18003661f  mov     rcx, [rbp+Handle]
0x180036623  mov     word ptr [rbp+var_40], ax
0x180036627  add     ax, r12w
0x18003662b  mov     word ptr [rbp+var_40+2], ax
0x18003662f  lea     rax, [rbp+arg_8]
0x180036633  mov     [rsp+80h+var_58], rax
0x180036638  mov     dword ptr [rsp+80h+var_60], ebx
0x18003663c  call    NtQueryValueKey
0x180036641  mov     ebx, eax
0x180036643  test    eax, eax
0x180036645  jns     short loc_18003666D
0x180036647  mov     rcx, gs:60h
0x180036650  mov     r8, rdi
0x180036653  xor     edx, edx
0x180036655  mov     rcx, [rcx+30h]
0x180036659  call    RtlFreeHeap_0
0x18003665e  jmp     loc_1800365A6
0x180036663  mov     eax, 0C0000017h
0x180036668  jmp     loc_1800365C8
0x18003666d  mov     eax, [rdi+0Ch]
0x180036670  mov     [r14], eax
0x180036673  jmp     short loc_180036647
```
