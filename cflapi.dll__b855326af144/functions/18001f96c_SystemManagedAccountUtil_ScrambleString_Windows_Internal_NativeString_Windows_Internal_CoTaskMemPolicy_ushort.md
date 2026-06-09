# SystemManagedAccountUtil::ScrambleString(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x18001f96c`
- end: `0x18001fb21`
- name: `?ScrambleString@SystemManagedAccountUtil@@YAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d29c`

## callees

- `0x1800067c4`
- `0x18001f5cc`
- `0x18001f96c`
- `0x1800215f8`
- `0x180021cbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18001fa0c`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18001fa0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f9d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fab7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001faf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fb08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f9d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fab7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001faf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fb08`

## pseudocode

```c
__int64 __fastcall SystemManagedAccountUtil::ScrambleString(_QWORD *a1)
{
  int v2; // ebx
  __int64 v3; // rdx
  unsigned __int64 v5; // rbx
  unsigned int v6; // esi
  __int64 v7; // r15
  int v8; // eax
  unsigned int v9; // r14d
  __int64 v10; // r8
  void *v11; // rbx
  int v12; // eax
  unsigned int v13; // edi
  LPVOID pv; // [rsp+20h] [rbp-28h] BYREF
  __int64 v15; // [rsp+28h] [rbp-20h]
  __int64 v16; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  __int16 v18; // [rsp+98h] [rbp+50h] BYREF
  __int16 v19; // [rsp+9Ah] [rbp+52h]

  pv = 0;
  v15 = 0;
  v16 = 0;
  v2 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         &pv,
         &dword_1800328FC,
         -1);
  if ( v2 >= 0 )
  {
    v5 = a1[1];
    if ( v5 == -1 )
    {
      if ( *a1 )
      {
        v5 = -1;
        do
          ++v5;
        while ( *(_WORD *)(*a1 + 2 * v5) );
      }
      else
      {
        v5 = 0;
      }
      a1[1] = v5;
    }
    v6 = 0;
    if ( v5 )
    {
      while ( 1 )
      {
        v7 = (unsigned int)(rand() % (v5 - v6));
        v18 = *(_WORD *)(*a1 + 2 * v7);
        v19 = 0;
        v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(&pv, &v18);
        v9 = v8;
        if ( v8 < 0 )
          break;
        if ( !(unsigned __int8)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::RemoveAt(
                                 a1,
                                 (unsigned int)v7) )
        {
          v2 = -2147418113;
          v3 = 66;
          goto LABEL_3;
        }
        if ( ++v6 >= v5 )
          goto LABEL_17;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
        (const char *)(unsigned int)v8,
        (int)pv);
      if ( pv )
        CoTaskMemFree(pv);
      return v9;
    }
    else
    {
LABEL_17:
      v10 = v15;
      v11 = pv;
      if ( v15 == -1 )
      {
        if ( pv )
        {
          v10 = -1;
          do
            ++v10;
          while ( *((_WORD *)pv + v10) );
        }
        else
        {
          v10 = 0;
        }
      }
      v12 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              a1,
              pv,
              v10);
      v13 = v12;
      if ( v12 >= 0 )
      {
        if ( v11 )
          CoTaskMemFree(v11);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x44,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
          (const char *)(unsigned int)v12,
          (int)pv);
        if ( v11 )
          CoTaskMemFree(v11);
        return v13;
      }
    }
  }
  else
  {
    v3 = 59;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SystemManagedAccountUtil.h",
      (const char *)(unsigned int)v2,
      (int)pv);
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)v2;
  }
}

```

## disassembly

```asm
0x18001f96c  push    rbp
0x18001f96e  push    rbx
0x18001f96f  push    rsi
0x18001f970  push    rdi
0x18001f971  push    r12
0x18001f973  push    r13
0x18001f975  push    r14
0x18001f977  push    r15
0x18001f979  mov     rbp, rsp
0x18001f97c  sub     rsp, 48h
0x18001f980  xor     r12d, r12d
0x18001f983  lea     rdx, dword_1800328FC
0x18001f98a  mov     rdi, rcx
0x18001f98d  mov     [rbp+pv], r12
0x18001f991  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001f995  mov     [rbp+var_20], r12
0x18001f999  mov     r8, r13
0x18001f99c  mov     [rbp+var_18], r12
0x18001f9a0  lea     rcx, [rbp+pv]
0x18001f9a4  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001f9a9  mov     ebx, eax
0x18001f9ab  test    eax, eax
0x18001f9ad  jns     short loc_18001F9DD
0x18001f9af  lea     edx, [r12+3Bh]; void *
0x18001f9b4  mov     rcx, [rbp+40h]; this
0x18001f9b8  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Syste"...
0x18001f9bf  mov     r9d, ebx; char *
0x18001f9c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f9c7  mov     rcx, [rbp+pv]; pv
0x18001f9cb  test    rcx, rcx
0x18001f9ce  jz      short loc_18001F9D6
0x18001f9d0  call    cs:__imp_CoTaskMemFree
0x18001f9d6  mov     eax, ebx
0x18001f9d8  jmp     loc_18001FB10
0x18001f9dd  mov     rbx, [rdi+8]
0x18001f9e1  cmp     rbx, r13
0x18001f9e4  jnz     short loc_18001FA04
0x18001f9e6  mov     rax, [rdi]
0x18001f9e9  test    rax, rax
0x18001f9ec  jz      short loc_18001F9FD
0x18001f9ee  mov     rbx, r13
0x18001f9f1  inc     rbx
0x18001f9f4  cmp     [rax+rbx*2], r12w
0x18001f9f9  jnz     short loc_18001F9F1
0x18001f9fb  jmp     short loc_18001FA00
0x18001f9fd  mov     rbx, r12
0x18001fa00  mov     [rdi+8], rbx
0x18001fa04  mov     esi, r12d
0x18001fa07  test    rbx, rbx
0x18001fa0a  jz      short loc_18001FA66
0x18001fa0c  call    cs:__imp_rand
0x18001fa12  mov     ecx, esi
0x18001fa14  xor     edx, edx
0x18001fa16  cdqe
0x18001fa18  mov     r8, rbx
0x18001fa1b  sub     r8, rcx
0x18001fa1e  div     r8
0x18001fa21  mov     rax, [rdi]
0x18001fa24  mov     r15d, edx
0x18001fa27  lea     rdx, [rbp+arg_8]
0x18001fa2b  movzx   ecx, word ptr [rax+r15*2]
0x18001fa30  xor     eax, eax
0x18001fa32  mov     [rbp+arg_8], cx
0x18001fa36  lea     rcx, [rbp+pv]
0x18001fa3a  mov     [rbp+arg_A], ax
0x18001fa3e  lea     r8d, [rax+1]
0x18001fa42  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18001fa47  mov     r14d, eax
0x18001fa4a  test    eax, eax
0x18001fa4c  js      short loc_18001FA96
0x18001fa4e  mov     edx, r15d
0x18001fa51  mov     rcx, rdi
0x18001fa54  call    ?RemoveAt@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAA_N_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::RemoveAt(unsigned __int64)
0x18001fa59  test    al, al
0x18001fa5b  jz      short loc_18001FA87
0x18001fa5d  inc     esi
0x18001fa5f  mov     eax, esi
0x18001fa61  cmp     rax, rbx
0x18001fa64  jb      short loc_18001FA0C
0x18001fa66  mov     r8, [rbp+var_20]
0x18001fa6a  mov     rbx, [rbp+pv]
0x18001fa6e  cmp     r8, r13
0x18001fa71  jnz     short loc_18001FAC5
0x18001fa73  test    rbx, rbx
0x18001fa76  jz      short loc_18001FAC2
0x18001fa78  mov     r8, r13
0x18001fa7b  inc     r8
0x18001fa7e  cmp     [rbx+r8*2], r12w
0x18001fa83  jnz     short loc_18001FA7B
0x18001fa85  jmp     short loc_18001FAC5
0x18001fa87  mov     ebx, 8000FFFFh
0x18001fa8c  mov     edx, 42h ; 'B'
0x18001fa91  jmp     loc_18001F9B4
0x18001fa96  mov     rcx, [rbp+40h]; this
0x18001fa9a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Syste"...
0x18001faa1  mov     r9d, r14d; char *
0x18001faa4  mov     edx, 41h ; 'A'; void *
0x18001faa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001faae  mov     rcx, [rbp+pv]; pv
0x18001fab2  test    rcx, rcx
0x18001fab5  jz      short loc_18001FABD
0x18001fab7  call    cs:__imp_CoTaskMemFree
0x18001fabd  mov     eax, r14d
0x18001fac0  jmp     short loc_18001FB10
0x18001fac2  mov     r8, r12
0x18001fac5  mov     rdx, rbx
0x18001fac8  mov     rcx, rdi
0x18001facb  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18001fad0  mov     edi, eax
0x18001fad2  test    eax, eax
0x18001fad4  jns     short loc_18001FB00
0x18001fad6  mov     rcx, [rbp+40h]; this
0x18001fada  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Syste"...
0x18001fae1  mov     r9d, eax; char *
0x18001fae4  mov     edx, 44h ; 'D'; void *
0x18001fae9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001faee  test    rbx, rbx
0x18001faf1  jz      short loc_18001FAFC
0x18001faf3  mov     rcx, rbx; pv
0x18001faf6  call    cs:__imp_CoTaskMemFree
0x18001fafc  mov     eax, edi
0x18001fafe  jmp     short loc_18001FB10
0x18001fb00  test    rbx, rbx
0x18001fb03  jz      short loc_18001FB0E
0x18001fb05  mov     rcx, rbx; pv
0x18001fb08  call    cs:__imp_CoTaskMemFree
0x18001fb0e  xor     eax, eax
0x18001fb10  add     rsp, 48h
0x18001fb14  pop     r15
0x18001fb16  pop     r14
0x18001fb18  pop     r13
0x18001fb1a  pop     r12
0x18001fb1c  pop     rdi
0x18001fb1d  pop     rsi
0x18001fb1e  pop     rbx
0x18001fb1f  pop     rbp
0x18001fb20  retn
```
