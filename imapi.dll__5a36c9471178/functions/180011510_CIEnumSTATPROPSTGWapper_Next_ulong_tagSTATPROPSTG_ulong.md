# CIEnumSTATPROPSTGWapper::Next(ulong,tagSTATPROPSTG *,ulong *)

- ea: `0x180011510`
- end: `0x180011737`
- name: `?Next@CIEnumSTATPROPSTGWapper@@UEAAJKPEAUtagSTATPROPSTG@@PEAK@Z`
- size: `551`
- prototype: `__int64 __fastcall(CIEnumSTATPROPSTGWapper *__hidden this, unsigned int, struct tagSTATPROPSTG *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180007bd4`
- `0x180011510`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18001160b`
- `ole32!CoTaskMemAlloc` at `0x18001160b`
- `KERNEL32!ReleaseMutex` at `0x18001171e`
- `KERNEL32!ReleaseMutex` at `0x18001171e`
- `KERNEL32!WaitForSingleObject` at `0x180011597`
- `KERNEL32!WaitForSingleObject` at `0x180011597`

## pseudocode

```c
__int64 __fastcall CIEnumSTATPROPSTGWapper::Next(
        CIEnumSTATPROPSTGWapper *this,
        unsigned int a2,
        struct tagSTATPROPSTG *a3,
        unsigned int *a4)
{
  unsigned int v8; // ebx
  void *v10; // rcx
  unsigned int v11; // r15d
  __int64 *v12; // rdi
  unsigned int v13; // eax
  __int64 v14; // r14
  __int64 v15; // rcx
  _WORD *v16; // rax
  _WORD *v17; // r8
  _WORD *v18; // r9
  __int64 v19; // rdx
  unsigned __int64 v20; // rdx
  __int64 v21; // rax
  _WORD *v22; // rcx
  __int64 v23; // r9

  if ( !a2 )
  {
    if ( a4 )
    {
      *a4 = 0;
      return 0;
    }
    return (unsigned int)-2147023116;
  }
  if ( a2 == 1 )
  {
    if ( !a3 )
      return (unsigned int)-2147023116;
  }
  else if ( !a3 || !a4 )
  {
    return (unsigned int)-2147023116;
  }
  if ( a4 )
    *a4 = 0;
  v10 = *(void **)(*((_QWORD *)this + 2) + 40LL);
  if ( v10 )
  {
    v11 = 0;
    v8 = 0;
    WaitForSingleObject(v10, 0xFFFFFFFF);
    if ( a2 )
    {
      do
      {
        v12 = *(__int64 **)(*((_QWORD *)this + 2) + 16LL);
        if ( !v12 )
          break;
        v13 = 0;
        while ( v13 < *((_DWORD *)this + 3) )
        {
          v12 = (__int64 *)*v12;
          ++v13;
          if ( !v12 )
            goto LABEL_46;
        }
        v14 = 2LL * v11;
        *((_DWORD *)&a3->propid + 2 * v14) = *((_DWORD *)v12 + 5);
        *((_WORD *)&a3->propid + 4 * v14 + 2) = *((_WORD *)v12 + 16);
        if ( *((_DWORD *)v12 + 4) )
        {
          *((_QWORD *)&a3->lpwstrName + 2 * v11) = 0;
        }
        else
        {
          v15 = -1;
          do
            ++v15;
          while ( *(_WORD *)(v12[3] + 2 * v15) );
          v16 = CoTaskMemAlloc(2 * v15 + 2);
          *((_QWORD *)&a3->lpwstrName + 2 * v11) = v16;
          v17 = v16;
          if ( !v16 )
          {
            v8 = -2147287032;
            break;
          }
          v18 = (_WORD *)v12[3];
          v19 = -1;
          do
            ++v19;
          while ( v18[v19] );
          v20 = v19 + 1;
          if ( !v20 )
          {
            v23 = 2147942487LL;
LABEL_41:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_de07cdecc1bf34ac651f6376ad8c6e00_Traceguids, v23);
            v8 = -2147286787;
            break;
          }
          if ( v20 > 0x7FFFFFFF )
          {
            v23 = 2147942487LL;
            *v16 = 0;
            goto LABEL_41;
          }
          v21 = 2147483646;
          do
          {
            if ( !v21 )
              break;
            if ( !*v18 )
              break;
            *v17++ = *v18++;
            --v21;
            --v20;
          }
          while ( v20 );
          v22 = v17 - 1;
          if ( v20 )
            v22 = v17;
          v23 = v20 == 0 ? 0x8007007A : 0;
          *v22 = 0;
          if ( !v20 )
            goto LABEL_41;
        }
        ++*((_DWORD *)this + 3);
        ++v11;
      }
      while ( v11 < a2 );
    }
LABEL_46:
    *a4 = v11;
    ReleaseMutex(*(HANDLE *)(*((_QWORD *)this + 2) + 40LL));
    if ( !v8 )
      return v11 < a2;
    return v8;
  }
  return 2147680264LL;
}

```

## disassembly

```asm
0x180011510  push    rbx
0x180011512  push    rbp
0x180011513  push    rsi
0x180011514  push    rdi
0x180011515  push    r12
0x180011517  push    r13
0x180011519  push    r14
0x18001151b  push    r15
0x18001151d  sub     rsp, 28h
0x180011521  xor     r14d, r14d
0x180011524  mov     rsi, r9
0x180011527  mov     rbp, r8
0x18001152a  mov     r12d, edx
0x18001152d  mov     r13, rcx
0x180011530  test    edx, edx
0x180011532  jnz     short loc_180011541
0x180011534  test    r9, r9
0x180011537  jz      short loc_180011550
0x180011539  mov     [r9], r14d
0x18001153c  mov     ebx, r14d
0x18001153f  jmp     short loc_180011555
0x180011541  mov     edi, 1
0x180011546  cmp     r12d, edi
0x180011549  jnz     short loc_180011568
0x18001154b  test    rbp, rbp
0x18001154e  jnz     short loc_180011572
0x180011550  mov     ebx, 800706F4h
0x180011555  mov     eax, ebx
0x180011557  add     rsp, 28h
0x18001155b  pop     r15
0x18001155d  pop     r14
0x18001155f  pop     r13
0x180011561  pop     r12
0x180011563  pop     rdi
0x180011564  pop     rsi
0x180011565  pop     rbp
0x180011566  pop     rbx
0x180011567  retn
0x180011568  test    rbp, rbp
0x18001156b  jz      short loc_180011550
0x18001156d  test    rsi, rsi
0x180011570  jz      short loc_180011550
0x180011572  test    rsi, rsi
0x180011575  jz      short loc_18001157A
0x180011577  mov     [r9], r14d
0x18001157a  mov     rax, [rcx+10h]
0x18001157e  mov     rcx, [rax+28h]; hHandle
0x180011582  test    rcx, rcx
0x180011585  jnz     short loc_18001158E
0x180011587  mov     eax, 80030008h
0x18001158c  jmp     short loc_180011557
0x18001158e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180011591  mov     r15d, r14d
0x180011594  mov     ebx, r14d
0x180011597  call    cs:__imp_WaitForSingleObject
0x18001159d  test    r12d, r12d
0x1800115a0  jz      loc_180011713
0x1800115a6  mov     rax, [r13+10h]
0x1800115aa  mov     rdi, [rax+10h]
0x1800115ae  test    rdi, rdi
0x1800115b1  jz      loc_18001170E
0x1800115b7  mov     eax, r14d
0x1800115ba  cmp     eax, [r13+0Ch]
0x1800115be  jnb     short loc_1800115CF
0x1800115c0  mov     rdi, [rdi]
0x1800115c3  inc     eax
0x1800115c5  test    rdi, rdi
0x1800115c8  jnz     short loc_1800115BA
0x1800115ca  jmp     loc_18001170E
0x1800115cf  mov     eax, [rdi+14h]
0x1800115d2  xor     edx, edx
0x1800115d4  mov     r14d, r15d
0x1800115d7  add     r14, r14
0x1800115da  mov     [rbp+r14*8+8], eax
0x1800115df  movzx   eax, word ptr [rdi+20h]
0x1800115e3  mov     [rbp+r14*8+0Ch], ax
0x1800115e9  cmp     [rdi+10h], edx
0x1800115ec  jnz     loc_18001169B
0x1800115f2  mov     rax, [rdi+18h]
0x1800115f6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800115fa  inc     rcx
0x1800115fd  cmp     [rax+rcx*2], dx
0x180011601  jnz     short loc_1800115FA
0x180011603  lea     rcx, ds:2[rcx*2]; cb
0x18001160b  call    cs:__imp_CoTaskMemAlloc
0x180011611  mov     [rbp+r14*8+0], rax
0x180011616  mov     r8, rax
0x180011619  xor     r14d, r14d
0x18001161c  test    rax, rax
0x18001161f  jz      loc_180011709
0x180011625  mov     r9, [rdi+18h]
0x180011629  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001162d  inc     rdx
0x180011630  cmp     [r9+rdx*2], r14w
0x180011635  jnz     short loc_18001162D
0x180011637  add     rdx, 1
0x18001163b  jz      loc_1800116C2
0x180011641  cmp     rdx, 7FFFFFFFh
0x180011648  ja      short loc_1800116BA
0x18001164a  mov     eax, 7FFFFFFEh
0x18001164f  test    rax, rax
0x180011652  jz      short loc_180011672
0x180011654  movzx   ecx, word ptr [r9]
0x180011658  test    cx, cx
0x18001165b  jz      short loc_180011672
0x18001165d  mov     [r8], cx
0x180011661  add     r9, 2
0x180011665  add     r8, 2
0x180011669  dec     rax
0x18001166c  sub     rdx, 1
0x180011670  jnz     short loc_18001164F
0x180011672  test    rdx, rdx
0x180011675  lea     rcx, [r8-2]
0x180011679  mov     rax, rdx
0x18001167c  cmovnz  rcx, r8
0x180011680  neg     rax
0x180011683  sbb     r9d, r9d
0x180011686  not     r9d
0x180011689  and     r9d, 8007007Ah
0x180011690  mov     [rcx], r14w
0x180011694  test    rdx, rdx
0x180011697  jz      short loc_1800116D1
0x180011699  jmp     short loc_1800116A3
0x18001169b  mov     [rbp+r14*8+0], rdx
0x1800116a0  xor     r14d, r14d
0x1800116a3  mov     edi, 1
0x1800116a8  add     [r13+0Ch], edi
0x1800116ac  add     r15d, edi
0x1800116af  cmp     r15d, r12d
0x1800116b2  jb      loc_1800115A6
0x1800116b8  jmp     short loc_180011713
0x1800116ba  mov     r9d, 80070057h
0x1800116c0  jmp     short loc_1800116CD
0x1800116c2  mov     r9d, 80070057h
0x1800116c8  test    rdx, rdx
0x1800116cb  jz      short loc_1800116D1
0x1800116cd  mov     [rax], r14w
0x1800116d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116d8  lea     rax, WPP_GLOBAL_Control
0x1800116df  mov     edi, 1
0x1800116e4  cmp     rcx, rax
0x1800116e7  jz      short loc_180011702
0x1800116e9  test    [rcx+44h], dil
0x1800116ed  jz      short loc_180011702
0x1800116ef  mov     rcx, [rcx+38h]
0x1800116f3  lea     edx, [rdi+9]
0x1800116f6  lea     r8, WPP_de07cdecc1bf34ac651f6376ad8c6e00_Traceguids
0x1800116fd  call    WPP_SF_d
0x180011702  mov     ebx, 800300FDh
0x180011707  jmp     short loc_180011713
0x180011709  mov     ebx, 80030008h
0x18001170e  mov     edi, 1
0x180011713  mov     [rsi], r15d
0x180011716  mov     rcx, [r13+10h]
0x18001171a  mov     rcx, [rcx+28h]; hMutex
0x18001171e  call    cs:__imp_ReleaseMutex
0x180011724  test    ebx, ebx
0x180011726  jnz     loc_180011555
0x18001172c  cmp     r15d, r12d
0x18001172f  cmovb   ebx, edi
0x180011732  jmp     loc_180011555
```
