# CatHelperRetrieveLongColumnAsStringVector(unsigned __int64,unsigned __int64,ulong,ulong,ushort * &,ushort * * &,ulong &)

- ea: `0x180001680`
- end: `0x180001943`
- name: `?CatHelperRetrieveLongColumnAsStringVector@@YAJ_K0KKAEAPEAGAEAPEAPEAGAEAK@Z`
- size: `707`
- prototype: `__int64 __usercall@<rax>(JET_SESID sesid@<rcx>, JET_TABLEID tableid@<rdx>, JET_COLUMNID columnid@<r8d>, unsigned int@<r9d>, unsigned __int16 **, unsigned __int16 ***, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800015cc`
- `0x180003570`

## callees

- `0x180001680`
- `0x180003538`
- `0x18000be40`
- `0x18000c7e8`
- `0x1800136c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001923`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001923`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800017ac`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800017f4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800017ac`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800017f4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000173d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000173d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001810`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800018f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001904`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001933`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001810`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800018f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001904`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001933`
- `ESENT!JetRetrieveColumn` at `0x1800016f7`
- `ESENT!JetRetrieveColumn` at `0x180001777`
- `ESENT!JetRetrieveColumn` at `0x1800016f7`
- `ESENT!JetRetrieveColumn` at `0x180001777`

## pseudocode

```c
__int64 __fastcall CatHelperRetrieveLongColumnAsStringVector(
        JET_SESID sesid,
        JET_TABLEID tableid,
        JET_COLUMNID columnid,
        __int64 a4,
        HLOCAL *a5,
        unsigned __int16 ***a6,
        unsigned int *a7)
{
  int v7; // esi
  JET_ERR v11; // eax
  unsigned int Column; // edi
  CHAR *v13; // rax
  CHAR *v14; // rbx
  int v15; // eax
  int v16; // ebp
  WCHAR *v17; // rax
  unsigned __int16 *v18; // r14
  _WORD *v19; // rax
  unsigned int v20; // ebp
  _WORD *v21; // rdx
  unsigned __int16 **v22; // rax
  __int64 v23; // rdx
  unsigned __int16 *v24; // rdi
  unsigned int i; // ebx
  unsigned __int16 *v26; // rax
  unsigned int pcbActual; // [rsp+48h] [rbp-50h] BYREF

  v7 = 0;
  *a6 = 0;
  *a7 = 0;
  *a5 = 0;
  pcbActual = 0;
  v11 = JetRetrieveColumn(sesid, tableid, columnid, 0, 0, &pcbActual, 1u, 0);
  Column = v11;
  if ( !v11 || v11 == 1004 || !pcbActual )
    return (unsigned int)-1003;
  if ( v11 == 1006 )
  {
    if ( pcbActual <= 0x3FFFFFFE )
    {
      v13 = (CHAR *)LocalAlloc(0x40u, pcbActual + 1);
      v14 = v13;
      if ( v13 )
      {
        Column = JetRetrieveColumn(sesid, tableid, columnid, v13, pcbActual, 0, 1u, 0);
        if ( Column )
          goto LABEL_12;
        v14[pcbActual] = 0;
        v15 = MultiByteToWideChar(0xFDE9u, 0, v14, -1, 0, 0);
        v16 = v15;
        if ( (unsigned int)(v15 - 1) <= 0x7FFFFFFD )
        {
          v17 = (WCHAR *)_CatDBAlloc(2LL * v15);
          v18 = v17;
          if ( v17 )
          {
            if ( MultiByteToWideChar(0xFDE9u, 0, v14, -1, v17, v16) )
            {
              v7 = v16 - 1;
              pcbActual = v16 - 1;
              *a5 = v18;
              goto LABEL_12;
            }
            LocalFree(v18);
          }
        }
        Column = -1011;
LABEL_12:
        LocalFree(v14);
        if ( Column )
          return Column;
        v19 = *a5;
        if ( *((_WORD *)*a5 + (unsigned int)(v7 - 1)) == 124 )
        {
          v20 = 0;
          v21 = &v19[v7];
          while ( v19 < v21 )
          {
            if ( *v19 == 124 )
            {
              if ( v19[1] == 124 )
                goto LABEL_33;
              ++v20;
            }
            ++v19;
          }
          v22 = (unsigned __int16 **)_CatDBAlloc(8LL * v20);
          *a6 = v22;
          if ( v22 )
          {
            memset_0(v22, 0, 8LL * v20);
            v24 = (unsigned __int16 *)*a5;
            for ( i = 0; i < v20; ++i )
            {
              v26 = wcschr(v24, v23);
              if ( !v26 )
                goto LABEL_33;
              *v26 = 0;
              v23 = i;
              (*a6)[v23] = v24;
              v24 = v26 + 1;
            }
            Column = 0;
            *a7 = i;
            return Column;
          }
          Column = -1011;
        }
        else
        {
LABEL_33:
          Column = -1003;
        }
        if ( *a5 )
          LocalFree(*a5);
        *a5 = 0;
        if ( *a6 )
          LocalFree(*a6);
        *a6 = 0;
        return Column;
      }
      SetLastError(0x8007000E);
    }
    return (unsigned int)-1011;
  }
  return Column;
}

```

## disassembly

```asm
0x180001680  mov     [rsp+arg_18], rbx
0x180001685  push    rbp
0x180001686  push    rsi
0x180001687  push    rdi
0x180001688  push    r12
0x18000168a  push    r13
0x18000168c  push    r14
0x18000168e  push    r15
0x180001690  sub     rsp, 60h
0x180001694  mov     rax, cs:__security_cookie
0x18000169b  xor     rax, rsp
0x18000169e  mov     [rsp+98h+var_48], rax
0x1800016a3  mov     rax, [rsp+98h+arg_30]
0x1800016ab  xor     esi, esi
0x1800016ad  mov     r13, [rsp+98h+arg_28]
0x1800016b5  xor     r9d, r9d; pvData
0x1800016b8  mov     r12, [rsp+98h+arg_20]
0x1800016c0  mov     r15d, r8d
0x1800016c3  mov     [rsp+98h+pretinfo], rsi; pretinfo
0x1800016c8  mov     r14, rdx
0x1800016cb  mov     [rsp+98h+var_58], rax
0x1800016d0  mov     rbp, rcx
0x1800016d3  mov     [r13+0], rsi
0x1800016d7  mov     [rax], esi
0x1800016d9  lea     rax, [rsp+98h+var_50]
0x1800016de  mov     [rsp+98h+grbit], 1; grbit
0x1800016e6  mov     [rsp+98h+pcbActual], rax; pcbActual
0x1800016eb  mov     [rsp+98h+cbData], esi; cbData
0x1800016ef  mov     [r12], rsi
0x1800016f3  mov     [rsp+98h+var_50], esi
0x1800016f7  call    cs:__imp_JetRetrieveColumn
0x1800016fd  mov     edi, eax
0x1800016ff  test    eax, eax
0x180001701  jz      loc_180001917
0x180001707  cmp     eax, 3ECh
0x18000170c  jz      loc_180001917
0x180001712  mov     eax, [rsp+98h+var_50]
0x180001716  test    eax, eax
0x180001718  jz      loc_180001917
0x18000171e  cmp     edi, 3EEh
0x180001724  jnz     loc_1800018BC
0x18000172a  cmp     eax, 3FFFFFFEh
0x18000172f  ja      loc_180001929
0x180001735  lea     edx, [rax+1]; uBytes
0x180001738  mov     ecx, 40h ; '@'; uFlags
0x18000173d  call    cs:__imp_LocalAlloc
0x180001743  mov     rbx, rax
0x180001746  test    rax, rax
0x180001749  jz      loc_18000191E
0x18000174f  xor     eax, eax
0x180001751  mov     r9, rbx; pvData
0x180001754  mov     [rsp+98h+pretinfo], rax; pretinfo
0x180001759  mov     r8d, r15d; columnid
0x18000175c  mov     [rsp+98h+grbit], 1; grbit
0x180001764  mov     rdx, r14; tableid
0x180001767  mov     [rsp+98h+pcbActual], rax; pcbActual
0x18000176c  mov     rcx, rbp; sesid
0x18000176f  mov     eax, [rsp+98h+var_50]
0x180001773  mov     [rsp+98h+cbData], eax; cbData
0x180001777  call    cs:__imp_JetRetrieveColumn
0x18000177d  xor     r15d, r15d
0x180001780  mov     edi, eax
0x180001782  test    eax, eax
0x180001784  jnz     loc_18000180D
0x18000178a  mov     eax, [rsp+98h+var_50]
0x18000178e  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x180001794  mov     dword ptr [rsp+98h+pcbActual], r15d; cchWideChar
0x180001799  mov     r8, rbx; lpMultiByteStr
0x18000179c  xor     edx, edx; dwFlags
0x18000179e  mov     qword ptr [rsp+98h+cbData], r15; lpWideCharStr
0x1800017a3  mov     ecx, 0FDE9h; CodePage
0x1800017a8  mov     [rax+rbx], sil
0x1800017ac  call    cs:__imp_MultiByteToWideChar
0x1800017b2  movsxd  rbp, eax
0x1800017b5  lea     ecx, [rbp-1]
0x1800017b8  cmp     ecx, 7FFFFFFDh
0x1800017be  ja      loc_180001939
0x1800017c4  mov     rcx, rbp
0x1800017c7  add     rcx, rcx; uBytes
0x1800017ca  call    ?_CatDBAlloc@@YAPEAX_K@Z; _CatDBAlloc(unsigned __int64)
0x1800017cf  mov     r14, rax
0x1800017d2  test    rax, rax
0x1800017d5  jz      loc_180001939
0x1800017db  mov     dword ptr [rsp+98h+pcbActual], ebp; cchWideChar
0x1800017df  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x1800017e5  mov     r8, rbx; lpMultiByteStr
0x1800017e8  mov     qword ptr [rsp+98h+cbData], rax; lpWideCharStr
0x1800017ed  xor     edx, edx; dwFlags
0x1800017ef  mov     ecx, 0FDE9h; CodePage
0x1800017f4  call    cs:__imp_MultiByteToWideChar
0x1800017fa  test    eax, eax
0x1800017fc  jz      loc_180001930
0x180001802  lea     esi, [rbp-1]
0x180001805  mov     [rsp+98h+var_50], esi
0x180001809  mov     [r12], r14
0x18000180d  mov     rcx, rbx; hMem
0x180001810  call    cs:__imp_LocalFree
0x180001816  test    edi, edi
0x180001818  jnz     loc_1800018BC
0x18000181e  mov     rax, [r12]
0x180001822  lea     ecx, [rsi-1]
0x180001825  cmp     word ptr [rax+rcx*2], 7Ch ; '|'
0x18000182a  jnz     loc_180001910
0x180001830  mov     ecx, esi
0x180001832  mov     ebp, r15d
0x180001835  lea     rdx, [rax+rcx*2]
0x180001839  nop     dword ptr [rax+00000000h]
0x180001840  cmp     rax, rdx
0x180001843  jnb     short loc_180001860
0x180001845  cmp     word ptr [rax], 7Ch ; '|'
0x180001849  jz      short loc_180001851
0x18000184b  add     rax, 2
0x18000184f  jmp     short loc_180001840
0x180001851  cmp     word ptr [rax+2], 7Ch ; '|'
0x180001856  jz      loc_180001910
0x18000185c  inc     ebp
0x18000185e  jmp     short loc_18000184B
0x180001860  mov     ebx, ebp
0x180001862  shl     rbx, 3
0x180001866  mov     rcx, rbx; uBytes
0x180001869  call    ?_CatDBAlloc@@YAPEAX_K@Z; _CatDBAlloc(unsigned __int64)
0x18000186e  mov     [r13+0], rax
0x180001872  test    rax, rax
0x180001875  jz      short loc_1800018E3
0x180001877  mov     r8, rbx; Size
0x18000187a  xor     edx, edx; Val
0x18000187c  mov     rcx, rax; void *
0x18000187f  call    memset_0
0x180001884  mov     rdi, [r12]
0x180001888  mov     ebx, r15d
0x18000188b  cmp     ebx, ebp
0x18000188d  jnb     short loc_1800018B2
0x18000188f  mov     rcx, rdi; unsigned __int16 *
0x180001892  call    ?wcschr@@YAPEAGPEAGG@Z; wcschr(ushort *,ushort)
0x180001897  test    rax, rax
0x18000189a  jz      short loc_180001910
0x18000189c  mov     [rax], r15w
0x1800018a0  mov     rcx, [r13+0]
0x1800018a4  mov     edx, ebx
0x1800018a6  inc     ebx
0x1800018a8  mov     [rcx+rdx*8], rdi
0x1800018ac  lea     rdi, [rax+2]
0x1800018b0  jmp     short loc_18000188B
0x1800018b2  mov     rax, [rsp+98h+var_58]
0x1800018b7  mov     edi, r15d
0x1800018ba  mov     [rax], ebx
0x1800018bc  mov     eax, edi
0x1800018be  mov     rcx, [rsp+98h+var_48]
0x1800018c3  xor     rcx, rsp; StackCookie
0x1800018c6  call    __security_check_cookie
0x1800018cb  mov     rbx, [rsp+98h+arg_18]
0x1800018d3  add     rsp, 60h
0x1800018d7  pop     r15
0x1800018d9  pop     r14
0x1800018db  pop     r13
0x1800018dd  pop     r12
0x1800018df  pop     rdi
0x1800018e0  pop     rsi
0x1800018e1  pop     rbp
0x1800018e2  retn
0x1800018e3  mov     edi, 0FFFFFC0Dh
0x1800018e8  mov     rcx, [r12]; hMem
0x1800018ec  test    rcx, rcx
0x1800018ef  jz      short loc_1800018F7
0x1800018f1  call    cs:__imp_LocalFree
0x1800018f7  mov     [r12], r15
0x1800018fb  mov     rcx, [r13+0]; hMem
0x1800018ff  test    rcx, rcx
0x180001902  jz      short loc_18000190A
0x180001904  call    cs:__imp_LocalFree
0x18000190a  mov     [r13+0], r15
0x18000190e  jmp     short loc_1800018BC
0x180001910  mov     edi, 0FFFFFC15h
0x180001915  jmp     short loc_1800018E8
0x180001917  mov     edi, 0FFFFFC15h
0x18000191c  jmp     short loc_1800018BC
0x18000191e  mov     ecx, 8007000Eh; dwErrCode
0x180001923  call    cs:__imp_SetLastError
0x180001929  mov     edi, 0FFFFFC0Dh
0x18000192e  jmp     short loc_1800018BC
0x180001930  mov     rcx, r14; hMem
0x180001933  call    cs:__imp_LocalFree
0x180001939  mov     edi, 0FFFFFC0Dh
0x18000193e  jmp     loc_18000180D
```
