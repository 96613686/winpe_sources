# GetNetResourceFromLocalPathW

- ea: `0x180010fa0`
- end: `0x18001146c`
- name: `GetNetResourceFromLocalPathW`
- size: `1228`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180066250`

## callees

- `0x180010fa0`
- `0x1800115cc`
- `0x180011790`
- `0x180011c80`
- `0x180011cb0`
- `0x1800254e0`
- `0x180025504`
- `0x1800259bc`
- `0x18002ac54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011092`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011092`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800110b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800110b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001105d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001105d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011158`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800113ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001139c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001139c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180011019`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180011019`
- `KERNEL32!lstrlenW` at `0x1800111d5`
- `KERNEL32!lstrlenW` at `0x1800111eb`
- `KERNEL32!lstrlenW` at `0x1800111d5`
- `KERNEL32!lstrlenW` at `0x1800111eb`
- `KERNEL32!GetComputerNameW` at `0x1800111c2`
- `KERNEL32!GetComputerNameW` at `0x1800111c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetNetResourceFromLocalPathW(__int64 a1, _DWORD *a2, unsigned int a3, _DWORD *a4)
{
  _DWORD *v5; // r12
  unsigned int v7; // r15d
  DWORD LastError; // edi
  CShareInfo **v9; // rax
  CShareInfo **v10; // r14
  LPBYTE v11; // rbp
  __int64 v12; // rbx
  BYTE *v13; // rdi
  CShareInfo *v14; // rdx
  CShareInfo *v15; // rcx
  CShareInfo *v16; // rcx
  void *v17; // rcx
  CShareInfo *i; // rbx
  int v20; // ecx
  __int64 v21; // rdi
  const WCHAR *v22; // rcx
  const WCHAR **v23; // rdx
  _WORD *v24; // r15
  unsigned int v25; // r11d
  __int64 v26; // r10
  __int64 v27; // r9
  __int64 v28; // rcx
  WCHAR *v29; // rdx
  WCHAR *v30; // r8
  WCHAR v31; // ax
  WCHAR *v32; // rcx
  __int16 *v33; // rcx
  __int16 **v34; // r8
  __int64 v35; // r8
  __int16 v36; // ax
  CShareInfo *v37; // rcx
  CShareInfo *v38; // rbx
  _WORD *v39; // rax
  int v40; // eax
  CShareInfo *v41; // rax
  CShareInfo *v42; // r12
  unsigned int v43; // edx
  CShareInfo **v44; // rax
  DWORD nSize; // [rsp+30h] [rbp-78h] BYREF
  _DWORD *v46; // [rsp+38h] [rbp-70h]
  _DWORD *v47; // [rsp+40h] [rbp-68h]
  WCHAR Buffer[16]; // [rsp+48h] [rbp-60h] BYREF

  v47 = a4;
  v5 = a2;
  v46 = a2;
  v7 = 0;
  LastError = 87;
  if ( !a1 || !a2 || !a4 || !a3 )
    goto LABEL_19;
  InitOnceExecuteOnce(&InitOnce, OneTimeInit, 0, 0);
  v9 = (CShareInfo **)operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  v10 = v9;
  if ( !v9 )
  {
    LastError = 14;
    goto LABEL_19;
  }
  v9[2] = (CShareInfo *)1;
  v9[3] = 0;
  *((_DWORD *)v9 + 8) = -1;
  *v9 = (CShareInfo *)v9;
  v9[1] = (CShareInfo *)v9;
  EnterCriticalSection(&CriticalSection);
  v11 = bufptr;
  nSize = 0;
  v12 = 0;
  if ( !g_ShareCache )
    goto LABEL_10;
  while ( 1 )
  {
    v13 = &v11[80 * v12];
    if ( (unsigned int)_o__wcsicmp(a1, *((_QWORD *)v13 + 5)) )
      goto LABEL_8;
    v39 = (_WORD *)*((_QWORD *)v13 + 5);
    if ( !v39 )
      goto LABEL_8;
    if ( !*v39 )
      goto LABEL_8;
    v40 = *((_DWORD *)v13 + 2);
    if ( (v40 & 0x3FFFFFFF) != 0 || v40 < 0 )
      goto LABEL_8;
    v41 = (CShareInfo *)operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
    v42 = v41;
    if ( !v41 )
      goto LABEL_9;
    *((_QWORD *)v41 + 2) = 1;
    *((_QWORD *)v41 + 3) = 0;
    *((_DWORD *)v41 + 8) = -1;
    *(_QWORD *)v41 = v41;
    *((_QWORD *)v41 + 1) = v41;
    if ( (int)CShareInfo::InitInstance(v41) < 0
      || (int)CShareInfo::Copy(v42, (const struct _SHARE_INFO_503 *)&v11[80 * v12]) < 0 )
    {
      break;
    }
    v44 = (CShareInfo **)v10[1];
    *(_QWORD *)v42 = v10;
    *((_QWORD *)v42 + 1) = v44;
    v10[1] = v42;
    *v44 = v42;
    ++nSize;
LABEL_8:
    v12 = (unsigned int)(v12 + 1);
    if ( (unsigned int)v12 >= g_ShareCache )
      goto LABEL_9;
  }
  CShareInfo::`scalar deleting destructor'(v42, v43);
LABEL_9:
  v5 = v46;
LABEL_10:
  LeaveCriticalSection(&CriticalSection);
  if ( nSize )
  {
    v14 = *v10;
    for ( i = *v10; ; i = *(CShareInfo **)i )
    {
      if ( i == (CShareInfo *)v10 )
      {
        for ( i = *v10; i != (CShareInfo *)v10; i = *(CShareInfo **)i )
        {
          if ( (*(_DWORD *)(*((_QWORD *)i + 3) + 8LL) & 0x3FFFFFFF) == 0 )
            goto LABEL_25;
        }
        goto LABEL_11;
      }
      v20 = *(_DWORD *)(*((_QWORD *)i + 3) + 8LL);
      if ( (v20 & 0x3FFFFFFF) == 0 && v20 >= 0 )
        break;
    }
LABEL_25:
    nSize = 16;
    if ( GetComputerNameW(Buffer, &nSize) )
    {
      v21 = (unsigned int)lstrlenW(Buffer);
      v22 = 0;
      v23 = (const WCHAR **)*((_QWORD *)i + 3);
      if ( v23 )
        v22 = *v23;
      if ( lstrlenW(v22) + (int)v21 + 4 > a3 )
      {
        LastError = 234;
        goto LABEL_12;
      }
      *v5 = 6029404;
      v24 = v5 + 1;
      v25 = a3 - 2;
      v26 = a3 - 2;
      v27 = 2147483646;
      if ( a3 - 3 > 0x7FFFFFFE )
      {
        if ( a3 != 2 )
          *v24 = 0;
      }
      else
      {
        v28 = 2147483646;
        v29 = Buffer;
        v30 = (WCHAR *)(v5 + 1);
        do
        {
          if ( !v28 )
            break;
          v31 = *v29;
          if ( !*v29 )
            break;
          ++v29;
          *v30++ = v31;
          --v28;
          --v26;
        }
        while ( v26 );
        v32 = v30 - 1;
        if ( v26 )
          v32 = v30;
        *v32 = 0;
      }
      v24[v21] = 92;
      v14 = (CShareInfo *)&v24[v21 + 1];
      v33 = 0;
      v34 = (__int16 **)*((_QWORD *)i + 3);
      if ( v34 )
        v33 = *v34;
      v35 = v25 - (unsigned int)v21 - 1;
      if ( v25 - (unsigned int)v21 - 2 > 0x7FFFFFFE )
      {
        if ( v25 - (_DWORD)v21 != 1 )
          *(_WORD *)v14 = 0;
      }
      else
      {
        do
        {
          if ( !v27 )
            break;
          v36 = *v33;
          if ( !*v33 )
            break;
          ++v33;
          *(_WORD *)v14 = v36;
          v14 = (CShareInfo *)((char *)v14 + 2);
          --v27;
          --v35;
        }
        while ( v35 );
        v37 = (CShareInfo *)((char *)v14 - 2);
        if ( v35 )
          v37 = v14;
        *(_WORD *)v37 = 0;
      }
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_12;
    }
    v7 = 1;
    *v47 = 0x20000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_6658e86926f336b363d5686ff3035642_Traceguids,
        a1,
        (__int64)v5);
  }
  else
  {
LABEL_11:
    LastError = 67;
  }
LABEL_12:
  v15 = *v10;
  if ( *v10 != (CShareInfo *)v10 )
  {
    do
    {
      v38 = *(CShareInfo **)v15;
      CShareInfo::`scalar deleting destructor'(v15, (unsigned int)v14);
      v15 = v38;
    }
    while ( v38 != (CShareInfo *)v10 );
  }
  if ( *((_DWORD *)v10 + 4) )
  {
    v16 = v10[3];
    if ( v16 )
    {
      operator delete(*((void **)v16 + 7));
      operator delete(*(void **)v10[3]);
      operator delete(*((void **)v10[3] + 2));
      operator delete(*((void **)v10[3] + 5));
      operator delete(*((void **)v10[3] + 6));
      v17 = (void *)*((_QWORD *)v10[3] + 9);
      if ( v17 )
        LocalFree(v17);
      operator delete(v10[3], (const struct std::nothrow_t *)0x50);
    }
  }
  operator delete(v10, (const struct std::nothrow_t *)0x28);
  if ( !v7 )
LABEL_19:
    SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x180010fa0  mov     [rsp+arg_10], rbx
0x180010fa5  push    rbp
0x180010fa6  push    rsi
0x180010fa7  push    rdi
0x180010fa8  push    r12
0x180010faa  push    r13
0x180010fac  push    r14
0x180010fae  push    r15
0x180010fb0  sub     rsp, 70h
0x180010fb4  mov     rax, cs:__security_cookie
0x180010fbb  xor     rax, rsp
0x180010fbe  mov     [rsp+0A8h+var_40], rax
0x180010fc3  mov     rax, r9
0x180010fc6  mov     [rsp+0A8h+var_68], rax
0x180010fcb  mov     r13d, r8d
0x180010fce  mov     r12, rdx
0x180010fd1  mov     [rsp+0A8h+var_70], rdx
0x180010fd6  mov     rsi, rcx
0x180010fd9  xor     r15d, r15d
0x180010fdc  mov     edi, 57h ; 'W'
0x180010fe1  test    rcx, rcx
0x180010fe4  jz      loc_180011156
0x180010fea  test    rdx, rdx
0x180010fed  jz      loc_180011156
0x180010ff3  test    rax, rax
0x180010ff6  jz      loc_180011156
0x180010ffc  test    r8d, r8d
0x180010fff  jz      loc_180011156
0x180011005  xor     r9d, r9d; Context
0x180011008  xor     r8d, r8d; Parameter
0x18001100b  lea     rdx, _OneTimeInit; InitFn
0x180011012  lea     rcx, InitOnce; InitOnce
0x180011019  call    cs:__imp_InitOnceExecuteOnce
0x18001101f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011026  mov     ecx, 28h ; '('; unsigned __int64
0x18001102b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011030  mov     r14, rax
0x180011033  test    rax, rax
0x180011036  jz      loc_180011392
0x18001103c  mov     qword ptr [rax+10h], 1
0x180011044  mov     [rax+18h], r15
0x180011048  mov     dword ptr [rax+20h], 0FFFFFFFFh
0x18001104f  mov     [rax], rax
0x180011052  mov     [rax+8], rax
0x180011056  lea     rcx, CriticalSection; lpCriticalSection
0x18001105d  call    cs:__imp_EnterCriticalSection
0x180011063  mov     rbp, cs:bufptr
0x18001106a  mov     [rsp+0A8h+nSize], r15d
0x18001106f  xor     ebx, ebx
0x180011071  cmp     cs:?g_ShareCache@@3VCShareCache@@A, ebx; CShareCache g_ShareCache
0x180011077  jbe     short loc_1800110AF
0x180011079  nop     dword ptr [rax+00000000h]
0x180011080  lea     rdi, [rbx+rbx*4]
0x180011084  shl     rdi, 4
0x180011088  add     rdi, rbp
0x18001108b  mov     rdx, [rdi+28h]
0x18001108f  mov     rcx, rsi
0x180011092  call    cs:__imp__o__wcsicmp
0x180011098  test    eax, eax
0x18001109a  jz      loc_1800112E6
0x1800110a0  inc     ebx
0x1800110a2  cmp     ebx, cs:?g_ShareCache@@3VCShareCache@@A; CShareCache g_ShareCache
0x1800110a8  jb      short loc_180011080
0x1800110aa  mov     r12, [rsp+0A8h+var_70]
0x1800110af  lea     rcx, CriticalSection; lpCriticalSection
0x1800110b6  call    cs:__imp_LeaveCriticalSection
0x1800110bc  cmp     [rsp+0A8h+nSize], r15d
0x1800110c1  ja      loc_180011186
0x1800110c7  mov     edi, 43h ; 'C'
0x1800110cc  mov     rcx, [r14]; this
0x1800110cf  cmp     rcx, r14
0x1800110d2  jnz     loc_1800112D0
0x1800110d8  cmp     dword ptr [r14+10h], 0
0x1800110dd  jz      short loc_180011144
0x1800110df  mov     rcx, [r14+18h]
0x1800110e3  test    rcx, rcx
0x1800110e6  jz      short loc_180011144
0x1800110e8  mov     rcx, [rcx+38h]; lpMem
0x1800110ec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800110f1  mov     rcx, [r14+18h]
0x1800110f5  mov     rcx, [rcx]; lpMem
0x1800110f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800110fd  mov     rcx, [r14+18h]
0x180011101  mov     rcx, [rcx+10h]; lpMem
0x180011105  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001110a  mov     rcx, [r14+18h]
0x18001110e  mov     rcx, [rcx+28h]; lpMem
0x180011112  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011117  mov     rcx, [r14+18h]
0x18001111b  mov     rcx, [rcx+30h]; lpMem
0x18001111f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011124  mov     rax, [r14+18h]
0x180011128  mov     rcx, [rax+48h]; hMem
0x18001112c  test    rcx, rcx
0x18001112f  jnz     loc_18001139C
0x180011135  mov     edx, 50h ; 'P'; struct std::nothrow_t *
0x18001113a  mov     rcx, [r14+18h]; void *
0x18001113e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011143  nop
0x180011144  mov     edx, 28h ; '('; struct std::nothrow_t *
0x180011149  mov     rcx, r14; void *
0x18001114c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011151  test    r15d, r15d
0x180011154  jnz     short loc_18001115E
0x180011156  mov     ecx, edi; dwErrCode
0x180011158  call    cs:__imp_SetLastError
0x18001115e  mov     eax, r15d
0x180011161  mov     rcx, [rsp+0A8h+var_40]
0x180011166  xor     rcx, rsp; StackCookie
0x180011169  call    __security_check_cookie
0x18001116e  mov     rbx, [rsp+0A8h+arg_10]
0x180011176  add     rsp, 70h
0x18001117a  pop     r15
0x18001117c  pop     r14
0x18001117e  pop     r13
0x180011180  pop     r12
0x180011182  pop     rdi
0x180011183  pop     rsi
0x180011184  pop     rbp
0x180011185  retn
0x180011186  mov     rdx, [r14]
0x180011189  mov     rbx, rdx
0x18001118c  cmp     rbx, r14
0x18001118f  jz      loc_1800113A8
0x180011195  mov     rax, [rbx+18h]
0x180011199  mov     ecx, [rax+8]
0x18001119c  test    ecx, 3FFFFFFFh
0x1800111a2  jnz     loc_18001138A
0x1800111a8  test    ecx, ecx
0x1800111aa  js      loc_18001138A
0x1800111b0  mov     [rsp+0A8h+nSize], 10h
0x1800111b8  lea     rdx, [rsp+0A8h+nSize]; nSize
0x1800111bd  lea     rcx, [rsp+0A8h+Buffer]; lpBuffer
0x1800111c2  call    cs:__imp_GetComputerNameW
0x1800111c8  test    eax, eax
0x1800111ca  jz      loc_1800113CA
0x1800111d0  lea     rcx, [rsp+0A8h+Buffer]; lpString
0x1800111d5  call    cs:__imp_lstrlenW
0x1800111db  mov     edi, eax
0x1800111dd  xor     ecx, ecx
0x1800111df  mov     rdx, [rbx+18h]
0x1800111e3  test    rdx, rdx
0x1800111e6  jz      short loc_1800111EB
0x1800111e8  mov     rcx, [rdx]; lpString
0x1800111eb  call    cs:__imp_lstrlenW
0x1800111f1  lea     ecx, [rdi+4]
0x1800111f4  add     ecx, eax
0x1800111f6  cmp     ecx, r13d
0x1800111f9  ja      loc_18001143B
0x1800111ff  mov     ebp, 5Ch ; '\'
0x180011204  mov     dword ptr [r12], 5C005Ch
0x18001120c  lea     r15, [r12+4]
0x180011211  lea     r11d, [r13-2]
0x180011215  mov     r10d, r11d
0x180011218  lea     eax, [r11-1]
0x18001121c  mov     r9d, 7FFFFFFEh
0x180011222  cmp     eax, r9d
0x180011225  ja      loc_180011445
0x18001122b  mov     ecx, r9d
0x18001122e  lea     rdx, [rsp+0A8h+Buffer]
0x180011233  mov     r8, r15
0x180011236  test    rcx, rcx
0x180011239  jz      short loc_180011258
0x18001123b  movzx   eax, word ptr [rdx]
0x18001123e  test    ax, ax
0x180011241  jz      short loc_180011258
0x180011243  add     rdx, 2
0x180011247  mov     [r8], ax
0x18001124b  add     r8, 2
0x18001124f  dec     rcx
0x180011252  sub     r10, 1
0x180011256  jnz     short loc_180011236
0x180011258  lea     rcx, [r8-2]
0x18001125c  test    r10, r10
0x18001125f  cmovnz  rcx, r8
0x180011263  xor     eax, eax
0x180011265  mov     [rcx], ax
0x180011268  mov     [r15+rdi*2], bp
0x18001126d  lea     rdx, [rdi+1]
0x180011271  lea     rdx, [r15+rdx*2]
0x180011275  sub     r11d, edi
0x180011278  lea     eax, [r11-1]
0x18001127c  xor     ecx, ecx
0x18001127e  mov     r8, [rbx+18h]
0x180011282  test    r8, r8
0x180011285  jz      short loc_18001128A
0x180011287  mov     rcx, [r8]
0x18001128a  mov     r8d, eax
0x18001128d  dec     eax
0x18001128f  cmp     eax, r9d
0x180011292  ja      loc_180011459
0x180011298  test    r9, r9
0x18001129b  jz      short loc_1800112B9
0x18001129d  movzx   eax, word ptr [rcx]
0x1800112a0  test    ax, ax
0x1800112a3  jz      short loc_1800112B9
0x1800112a5  add     rcx, 2
0x1800112a9  mov     [rdx], ax
0x1800112ac  add     rdx, 2
0x1800112b0  dec     r9
0x1800112b3  sub     r8, 1
0x1800112b7  jnz     short loc_180011298
0x1800112b9  lea     rcx, [rdx-2]
0x1800112bd  test    r8, r8
0x1800112c0  cmovnz  rcx, rdx
0x1800112c4  xor     eax, eax
0x1800112c6  mov     [rcx], ax
0x1800112c9  xor     edi, edi
0x1800112cb  jmp     loc_1800113DA
0x1800112d0  mov     rbx, [rcx]
0x1800112d3  call    ??_GCShareInfo@@QEAAPEAXI@Z; CShareInfo::`scalar deleting destructor'(uint)
0x1800112d8  mov     rcx, rbx
0x1800112db  cmp     rbx, r14
0x1800112de  jz      loc_1800110D8
0x1800112e4  jmp     short loc_1800112D0
0x1800112e6  mov     rax, [rdi+28h]
0x1800112ea  test    rax, rax
0x1800112ed  jz      loc_1800110A0
0x1800112f3  cmp     [rax], r15w
0x1800112f7  jz      loc_1800110A0
0x1800112fd  mov     eax, [rdi+8]
0x180011300  test    eax, 3FFFFFFFh
0x180011305  jnz     loc_1800110A0
0x18001130b  test    eax, eax
0x18001130d  js      loc_1800110A0
0x180011313  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001131a  mov     ecx, 28h ; '('; unsigned __int64
0x18001131f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180011324  mov     r12, rax
0x180011327  test    rax, rax
0x18001132a  jz      loc_1800110AA
0x180011330  mov     qword ptr [rax+10h], 1
0x180011338  mov     [rax+18h], r15
0x18001133c  mov     dword ptr [rax+20h], 0FFFFFFFFh
0x180011343  mov     [rax], rax
0x180011346  mov     [rax+8], rax
0x18001134a  mov     rcx, rax; this
0x18001134d  call    ?InitInstance@CShareInfo@@QEAAJXZ; CShareInfo::InitInstance(void)
0x180011352  test    eax, eax
0x180011354  js      loc_18001142E
0x18001135a  mov     rdx, rdi; struct _SHARE_INFO_503 *
0x18001135d  mov     rcx, r12; this
0x180011360  call    ?Copy@CShareInfo@@QEAAJPEBU_SHARE_INFO_503@@@Z; CShareInfo::Copy(_SHARE_INFO_503 const *)
0x180011365  test    eax, eax
0x180011367  js      loc_18001142E
0x18001136d  mov     rax, [r14+8]
0x180011371  mov     [r12], r14
0x180011375  mov     [r12+8], rax
0x18001137a  mov     [r14+8], r12
0x18001137e  mov     [rax], r12
0x180011381  inc     [rsp+0A8h+nSize]
0x180011385  jmp     loc_1800110A0
0x18001138a  mov     rbx, [rbx]
0x18001138d  jmp     loc_18001118C
0x180011392  mov     edi, 0Eh
0x180011397  jmp     loc_180011156
0x18001139c  call    cs:__imp_LocalFree
0x1800113a2  nop
0x1800113a3  jmp     loc_180011135
0x1800113a8  mov     rbx, rdx
0x1800113ab  cmp     rbx, r14
0x1800113ae  jz      loc_1800110C7
0x1800113b4  mov     rax, [rbx+18h]
0x1800113b8  test    dword ptr [rax+8], 3FFFFFFFh
0x1800113bf  jz      loc_1800111B0
0x1800113c5  mov     rbx, [rbx]
0x1800113c8  jmp     short loc_1800113AB
0x1800113ca  call    cs:__imp_GetLastError
0x1800113d0  mov     edi, eax
0x1800113d2  test    eax, eax
0x1800113d4  jnz     loc_1800110CC
0x1800113da  mov     r15d, 1
0x1800113e0  mov     rax, [rsp+0A8h+var_68]
0x1800113e5  mov     dword ptr [rax], 20000h
0x1800113eb  lea     rax, WPP_GLOBAL_Control
0x1800113f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113f9  cmp     rcx, rax
0x1800113fc  jz      loc_1800110CC
0x180011402  test    byte ptr [rcx+1Ch], 8
0x180011406  jz      loc_1800110CC
0x18001140c  mov     edx, 0Ah
0x180011411  mov     [rsp+0A8h+var_88], r12
0x180011416  mov     r9, rsi
0x180011419  lea     r8, WPP_6658e86926f336b363d5686ff3035642_Traceguids
0x180011420  mov     rcx, [rcx+10h]
0x180011424  call    WPP_SF_SS
0x180011429  jmp     loc_1800110CC
0x18001142e  mov     rcx, r12; this
0x180011431  call    ??_GCShareInfo@@QEAAPEAXI@Z; CShareInfo::`scalar deleting destructor'(uint)
0x180011436  jmp     loc_1800110AA
0x18001143b  mov     edi, 0EAh
0x180011440  jmp     loc_1800110CC
0x180011445  test    r11d, r11d
0x180011448  jz      loc_180011268
0x18001144e  xor     eax, eax
0x180011450  mov     [r15], ax
0x180011454  jmp     loc_180011268
0x180011459  test    r8, r8
0x18001145c  jz      loc_1800112C9
0x180011462  xor     eax, eax
  ... truncated ...
```
