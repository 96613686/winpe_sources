# Dfdll::CPath::PathAddTail(Dfdll::CString &,ushort const *)

- ea: `0x180003530`
- end: `0x1800036c8`
- name: `?PathAddTail@CPath@Dfdll@@SAJAEAVCString@2@PEBG@Z`
- size: `408`
- prototype: `__int64 __fastcall(struct Dfdll::CString *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ab8c`
- `0x18000cac8`

## callees

- `0x180002238`
- `0x180003530`

## pseudocode

```c
__int64 __fastcall Dfdll::CPath::PathAddTail(struct Dfdll::CString *this, struct std::nothrow_t *a2)
{
  int v2; // r11d
  struct std::nothrow_t *v3; // rdi
  signed int v5; // ebx
  __int64 v6; // r10
  const unsigned __int16 *v7; // rax
  __int64 v8; // rdx
  unsigned int v9; // r8d
  __int64 v10; // r9
  __int64 v11; // rdx
  const unsigned __int16 *v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  struct std::nothrow_t *v15; // rax

  v2 = *((_DWORD *)this + 8);
  v3 = a2;
  if ( a2 && (v6 = *((_QWORD *)this + 2)) != 0 )
  {
    v7 = (const unsigned __int16 *)a2;
    v8 = 0x7FFFFFFF;
    do
    {
      if ( !*v7 )
        break;
      ++v7;
      --v8;
    }
    while ( v8 );
    v9 = v8 == 0 ? 0x80070057 : 0;
    v10 = (0x7FFFFFFF - v8) & -(__int64)(v8 != 0);
    if ( !v8 )
      return v9;
    if ( !(_DWORD)v10 )
      return 0;
    if ( *(_WORD *)v3 == 92 )
    {
      v3 = (struct std::nothrow_t *)((char *)v3 + 2);
      if ( (_DWORD)v10 == 1 )
        return 0;
    }
    if ( v2 && *(_WORD *)(v6 + 2LL * (unsigned int)(v2 - 1)) != 92 )
    {
      v11 = 0x7FFFFFFF;
      v12 = L"\\";
      do
      {
        if ( !*v12 )
          break;
        ++v12;
        --v11;
      }
      while ( v11 );
      v9 = v11 == 0 ? 0x80070057 : 0;
      if ( !v11 )
        return v9;
      v13 = Dfdll::CString::Append(this, (struct std::nothrow_t *)L"\\", v11 != 0 ? 0x7FFFFFFF - v11 : 0);
      if ( v13 < 0 )
        return (unsigned int)v13;
    }
    if ( !v3 )
      return 0;
    v14 = 0x7FFFFFFF;
    v15 = v3;
    do
    {
      if ( !*(_WORD *)v15 )
        break;
      v15 = (struct std::nothrow_t *)((char *)v15 + 2);
      --v14;
    }
    while ( v14 );
    v5 = v14 == 0 ? 0x80070057 : 0;
    if ( v14 )
    {
      v5 = Dfdll::CString::Append(this, v3, v14 != 0 ? 0x7FFFFFFF - v14 : 0);
      if ( v5 >= 0 )
        return 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180003530  mov     rax, rsp
0x180003533  mov     [rax+8], rbx
0x180003537  mov     [rax+10h], rbp
0x18000353b  mov     [rax+18h], rsi
0x18000353f  mov     [rax+20h], rdi
0x180003543  push    r14
0x180003545  sub     rsp, 20h
0x180003549  mov     r11d, [rcx+20h]
0x18000354d  xor     r14d, r14d
0x180003550  mov     rdi, rdx
0x180003553  mov     rbp, rcx
0x180003556  test    rdx, rdx
0x180003559  jnz     short loc_180003565
0x18000355b  mov     ebx, 80070057h
0x180003560  jmp     loc_1800036AB
0x180003565  mov     r10, [rcx+10h]
0x180003569  test    r10, r10
0x18000356c  jz      short loc_18000355B
0x18000356e  mov     esi, 7FFFFFFFh
0x180003573  mov     rax, rdi
0x180003576  mov     edx, esi
0x180003578  cmp     [rax], r14w
0x18000357c  jz      short loc_180003588
0x18000357e  add     rax, 2
0x180003582  sub     rdx, 1
0x180003586  jnz     short loc_180003578
0x180003588  mov     rax, rdx
0x18000358b  mov     ebx, 80070057h
0x180003590  neg     rax
0x180003593  mov     rcx, rsi
0x180003596  mov     rax, rdx
0x180003599  sbb     r8d, r8d
0x18000359c  sub     rcx, rdx
0x18000359f  not     r8d
0x1800035a2  and     r8d, ebx
0x1800035a5  neg     rax
0x1800035a8  sbb     r9, r9
0x1800035ab  and     r9, rcx
0x1800035ae  test    rdx, rdx
0x1800035b1  jnz     short loc_1800035BB
0x1800035b3  mov     ebx, r8d
0x1800035b6  jmp     loc_1800036AB
0x1800035bb  test    r9d, r9d
0x1800035be  jz      loc_1800036A8
0x1800035c4  cmp     word ptr [rdi], 5Ch ; '\'
0x1800035c8  jnz     short loc_1800035EA
0x1800035ca  add     rdi, 2
0x1800035ce  cmp     r9d, 1
0x1800035d2  jnb     short loc_1800035DE
0x1800035d4  mov     ebx, 80070216h
0x1800035d9  jmp     loc_1800036AB
0x1800035de  lea     eax, [r9-1]
0x1800035e2  test    eax, eax
0x1800035e4  jz      loc_1800036A8
0x1800035ea  test    r11d, r11d
0x1800035ed  jz      short loc_180003659
0x1800035ef  lea     eax, [r11-1]
0x1800035f3  cmp     word ptr [r10+rax*2], 5Ch ; '\'
0x1800035f9  jz      short loc_180003659
0x1800035fb  mov     rdx, rsi
0x1800035fe  lea     rax, asc_180020AE0; "\\"
0x180003605  cmp     [rax], r14w
0x180003609  jz      short loc_180003615
0x18000360b  add     rax, 2
0x18000360f  sub     rdx, 1
0x180003613  jnz     short loc_180003605
0x180003615  mov     rax, rdx
0x180003618  mov     rcx, rsi
0x18000361b  neg     rax
0x18000361e  mov     rax, rdx
0x180003621  sbb     r8d, r8d
0x180003624  sub     rcx, rdx
0x180003627  not     r8d
0x18000362a  and     r8d, ebx
0x18000362d  neg     rax
0x180003630  sbb     r9, r9
0x180003633  and     r9, rcx
0x180003636  test    rdx, rdx
0x180003639  jz      loc_1800035B3
0x18000363f  mov     r8d, r9d; unsigned int
0x180003642  lea     rdx, asc_180020AE0; "\\"
0x180003649  mov     rcx, rbp; this
0x18000364c  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x180003651  test    eax, eax
0x180003653  jns     short loc_180003659
0x180003655  mov     ebx, eax
0x180003657  jmp     short loc_1800036AB
0x180003659  test    rdi, rdi
0x18000365c  jz      short loc_1800036A8
0x18000365e  mov     rdx, rsi
0x180003661  mov     rax, rdi
0x180003664  cmp     [rax], r14w
0x180003668  jz      short loc_180003674
0x18000366a  add     rax, 2
0x18000366e  sub     rdx, 1
0x180003672  jnz     short loc_180003664
0x180003674  mov     rax, rdx
0x180003677  neg     rax
0x18000367a  mov     rax, rdx
0x18000367d  sbb     ecx, ecx
0x18000367f  sub     rsi, rdx
0x180003682  not     ecx
0x180003684  and     ebx, ecx
0x180003686  neg     rax
0x180003689  sbb     rcx, rcx
0x18000368c  and     rcx, rsi
0x18000368f  test    rdx, rdx
0x180003692  jz      short loc_1800036AB
0x180003694  mov     r8d, ecx; unsigned int
0x180003697  mov     rdx, rdi; unsigned __int16 *
0x18000369a  mov     rcx, rbp; this
0x18000369d  call    ?Append@CString@Dfdll@@QEAAJPEBGI@Z; Dfdll::CString::Append(ushort const *,uint)
0x1800036a2  mov     ebx, eax
0x1800036a4  test    eax, eax
0x1800036a6  js      short loc_1800036AB
0x1800036a8  mov     ebx, r14d
0x1800036ab  mov     rbp, [rsp+28h+arg_8]
0x1800036b0  mov     eax, ebx
0x1800036b2  mov     rbx, [rsp+28h+arg_0]
0x1800036b7  mov     rsi, [rsp+28h+arg_10]
0x1800036bc  mov     rdi, [rsp+28h+arg_18]
0x1800036c1  add     rsp, 20h
0x1800036c5  pop     r14
0x1800036c7  retn
```
