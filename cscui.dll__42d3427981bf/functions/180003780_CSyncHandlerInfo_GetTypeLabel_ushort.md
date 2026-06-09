# CSyncHandlerInfo::GetTypeLabel(ushort * *)

- ea: `0x180003780`
- end: `0x18000393f`
- name: `?GetTypeLabel@CSyncHandlerInfo@@UEAAJPEAPEAG@Z`
- size: `447`
- prototype: `__int64 __fastcall(CSyncHandlerInfo *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003780`
- `0x180003a90`
- `0x180008b40`
- `0x18001101c`
- `0x180013d9c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000389d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000389d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800037f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800037f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003865`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003865`

## pseudocode

```c
__int64 __fastcall CSyncHandlerInfo::GetTypeLabel(CSyncHandlerInfo *this, LPVOID *a2)
{
  int v4; // ebx
  unsigned __int16 *v5; // rbx
  __int64 v6; // rdi
  unsigned __int64 v7; // rdi
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rdx
  __int64 v10; // rcx
  unsigned __int16 *v11; // rcx
  int v12; // ecx
  void *v13; // rdi
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500035LL;
  lpMem = 0;
  v4 = CscUtil_FormatStringID((LPWSTR)&lpMem, g_hInstance, 0x10F2u);
  if ( v4 < 0 )
    goto LABEL_30;
  v5 = (unsigned __int16 *)lpMem;
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)lpMem + v6) );
  v7 = v6 + 1;
  v8 = (unsigned __int16 *)CoTaskMemAlloc(2 * v7);
  *a2 = v8;
  v9 = v8;
  if ( !v8 )
  {
    v4 = -2147024882;
    goto LABEL_22;
  }
  if ( v7 )
  {
    if ( v7 > 0x7FFFFFFF )
    {
      v4 = -2147024809;
      *v8 = 0;
      goto LABEL_18;
    }
    v10 = 2147483646;
    do
    {
      if ( !v10 )
        break;
      if ( !*v5 )
        break;
      *v9++ = *v5++;
      --v10;
      --v7;
    }
    while ( v7 );
    v11 = v9 - 1;
    if ( v7 )
      v11 = v9;
    *v11 = 0;
    v12 = -2147024774;
    if ( v7 )
      v12 = 0;
  }
  else
  {
    v12 = -2147024809;
  }
  v4 = v12;
  if ( v12 < 0 )
  {
LABEL_18:
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
LABEL_22:
  v13 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    if ( ProcessHeap )
    {
      if ( !HeapFree(ProcessHeap, 0, v13) )
        ResultFromLastError();
    }
  }
  if ( v4 < 0 )
  {
LABEL_30:
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids,
        (unsigned int)v4);
    }
    return (unsigned int)v4;
  }
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids, *a2);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003780  push    rsi
0x180003782  sub     rsp, 20h
0x180003786  mov     rsi, rdx
0x180003789  test    rdx, rdx
0x18000378c  jnz     short loc_180003798
0x18000378e  mov     eax, 80004003h
0x180003793  jmp     loc_180003939
0x180003798  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000379f  lea     rcx, [rsp+28h+lpMem]; lpBuffer
0x1800037a4  mov     r8d, 10F2h; uID
0x1800037aa  mov     [rsp+28h+arg_0], rbx
0x1800037af  mov     [rsp+28h+lpMem], 0
0x1800037b8  call    ?CscUtil_FormatStringID@@YAJPEAPEAGPEAUHINSTANCE__@@IZZ; CscUtil_FormatStringID(ushort * *,HINSTANCE__ *,uint,...)
0x1800037bd  mov     ebx, eax
0x1800037bf  test    eax, eax
0x1800037c1  js      loc_1800038FE
0x1800037c7  mov     rbx, [rsp+28h+lpMem]
0x1800037cc  mov     [rsp+28h+arg_10], rdi
0x1800037d1  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x1800037d8  nop     dword ptr [rax+rax+00000000h]
0x1800037e0  inc     rdi
0x1800037e3  cmp     word ptr [rbx+rdi*2], 0
0x1800037e8  jnz     short loc_1800037E0
0x1800037ea  inc     rdi
0x1800037ed  lea     rcx, [rdi+rdi]; cb
0x1800037f1  call    cs:__imp_CoTaskMemAlloc
0x1800037f7  mov     [rsi], rax
0x1800037fa  mov     rdx, rax
0x1800037fd  test    rax, rax
0x180003800  jz      loc_18000388E
0x180003806  test    rdi, rdi
0x180003809  jz      short loc_18000387B
0x18000380b  cmp     rdi, 7FFFFFFFh
0x180003812  ja      short loc_180003874
0x180003814  mov     ecx, 7FFFFFFEh
0x180003819  nop     dword ptr [rax+00000000h]
0x180003820  test    rcx, rcx
0x180003823  jz      short loc_180003841
0x180003825  movzx   eax, word ptr [rbx]
0x180003828  test    ax, ax
0x18000382b  jz      short loc_180003841
0x18000382d  mov     [rdx], ax
0x180003830  add     rbx, 2
0x180003834  add     rdx, 2
0x180003838  dec     rcx
0x18000383b  sub     rdi, 1
0x18000383f  jnz     short loc_180003820
0x180003841  test    rdi, rdi
0x180003844  lea     rcx, [rdx-2]
0x180003848  cmovnz  rcx, rdx
0x18000384c  xor     eax, eax
0x18000384e  test    rdi, rdi
0x180003851  mov     [rcx], ax
0x180003854  mov     ecx, 8007007Ah
0x180003859  cmovnz  ecx, eax
0x18000385c  mov     ebx, ecx
0x18000385e  test    ecx, ecx
0x180003860  jns     short loc_180003893
0x180003862  mov     rcx, [rsi]; pv
0x180003865  call    cs:__imp_CoTaskMemFree
0x18000386b  mov     qword ptr [rsi], 0
0x180003872  jmp     short loc_180003893
0x180003874  mov     ebx, 80070057h
0x180003879  jmp     short loc_180003887
0x18000387b  mov     ebx, 80070057h
0x180003880  mov     ecx, ebx
0x180003882  test    rdi, rdi
0x180003885  jz      short loc_18000385C
0x180003887  xor     eax, eax
0x180003889  mov     [rdx], ax
0x18000388c  jmp     short loc_180003862
0x18000388e  mov     ebx, 8007000Eh
0x180003893  mov     rdi, [rsp+28h+lpMem]
0x180003898  test    rdi, rdi
0x18000389b  jz      short loc_1800038BF
0x18000389d  call    cs:__imp_GetProcessHeap
0x1800038a3  test    rax, rax
0x1800038a6  jz      short loc_1800038BF
0x1800038a8  mov     r8, rdi; lpMem
0x1800038ab  xor     edx, edx; dwFlags
0x1800038ad  mov     rcx, rax; hHeap
0x1800038b0  call    cs:__imp_HeapFree
0x1800038b6  test    eax, eax
0x1800038b8  jnz     short loc_1800038BF
0x1800038ba  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800038bf  mov     rdi, [rsp+28h+arg_10]
0x1800038c4  test    ebx, ebx
0x1800038c6  js      short loc_1800038FE
0x1800038c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038cf  lea     rax, WPP_GLOBAL_Control
0x1800038d6  cmp     rcx, rax
0x1800038d9  jz      short loc_180003932
0x1800038db  test    dword ptr [rcx+1Ch], 100000h
0x1800038e2  jz      short loc_180003932
0x1800038e4  mov     r9, [rsi]
0x1800038e7  lea     r8, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x1800038ee  mov     rcx, [rcx+10h]
0x1800038f2  mov     edx, 3Ah ; ':'
0x1800038f7  call    WPP_SF_S
0x1800038fc  jmp     short loc_180003932
0x1800038fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180003905  lea     rax, WPP_GLOBAL_Control
0x18000390c  cmp     rcx, rax
0x18000390f  jz      short loc_180003932
0x180003911  test    dword ptr [rcx+1Ch], 100000h
0x180003918  jz      short loc_180003932
0x18000391a  mov     rcx, [rcx+10h]
0x18000391e  lea     r8, WPP_3547be1ff7953ef71cbc2f6fb32b1b7c_Traceguids
0x180003925  mov     edx, 3Bh ; ';'
0x18000392a  mov     r9d, ebx
0x18000392d  call    WPP_SF_d
0x180003932  mov     eax, ebx
0x180003934  mov     rbx, [rsp+28h+arg_0]
0x180003939  add     rsp, 20h
0x18000393d  pop     rsi
0x18000393e  retn
```
