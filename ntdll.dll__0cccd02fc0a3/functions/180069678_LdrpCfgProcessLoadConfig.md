# LdrpCfgProcessLoadConfig

- ea: `0x180069678`
- end: `0x180069cb9`
- name: `LdrpCfgProcessLoadConfig`
- size: `1601`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800693a8`
- `0x180136ed4`

## callees

- `0x180066020`
- `0x180066cf0`
- `0x180068ee4`
- `0x180069678`
- `0x1800e7544`
- `0x18012ac70`
- `0x18015ecd0`
- `0x180162000`
- `0x18016f020`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall LdrpCfgProcessLoadConfig(__int64 a1, unsigned __int16 *a2, __int64 a3)
{
  __int64 (__fastcall **v6)(); // r15
  size_t v7; // rdi
  unsigned __int64 v8; // rcx
  bool v9; // cf
  unsigned __int64 v10; // rdx
  int v11; // r14d
  __int64 (__fastcall **v12)(); // r12
  __int64 (__fastcall **v13)(); // r14
  __int64 (__fastcall **v14)(); // r13
  size_t v15; // rbx
  __int64 (__fastcall *v16)(); // rax
  __int64 result; // rax
  __int64 v18; // r8
  unsigned __int64 v19; // rcx
  __int64 v20; // rax
  unsigned __int64 v21; // rcx
  __int64 v22; // rax
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rcx
  __int64 v25; // rax
  unsigned __int64 v26; // rcx
  __int64 v27; // rax
  unsigned __int64 v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  int v31; // eax
  unsigned int v32; // [rsp+30h] [rbp-79h] BYREF
  int v33; // [rsp+34h] [rbp-75h] BYREF
  __int64 v34; // [rsp+38h] [rbp-71h] BYREF
  __int64 v35; // [rsp+40h] [rbp-69h] BYREF
  __int64 (__fastcall **v36)(); // [rsp+48h] [rbp-61h]
  __int64 (__fastcall **v37)(); // [rsp+50h] [rbp-59h]
  unsigned __int64 Base; // [rsp+60h] [rbp-49h] BYREF
  _QWORD v39[11]; // [rsp+68h] [rbp-41h]

  memset_thunk_772440563353939046(&Base, 0, 0x60u);
  v6 = 0;
  v32 = 0;
  v35 = 0;
  v34 = 0;
  if ( a3 && *(_DWORD *)a3 >= 0x94u )
  {
    v37 = 0;
    v7 = 0;
    v8 = *(unsigned __int16 *)(a3 + 78) & (((LdrpPolicyBits & 4) != 0 ? 32512 : 31488) | 0x8000u);
    v9 = (LdrpPolicyBits & 4) != 0;
    v10 = -(LdrpPolicyBits & 4);
    *(_DWORD *)(a1 + 280) = v8;
    if ( ((v9 ? 32512 : 31488) & (unsigned int)v8) != 0 && (unsigned __int8)LdrpIsModuleUnderSystem32(a1, v10) )
    {
      v30 = *(_DWORD *)(a1 + 280);
      if ( a1 == LdrpImageEntry )
        v31 = v30 | 0x200;
      else
        v31 = v30 | 0x100;
      *(_DWORD *)(a1 + 280) = v31;
    }
    if ( (*(_DWORD *)(a3 + 144) & 0x1000) != 0 )
    {
      *(_DWORD *)(a1 + 104) |= 0x8000u;
      if ( (*(_DWORD *)(a3 + 144) & 0x2000) != 0 )
      {
        v18 = RtlImageDirectoryEntryToData(*(_QWORD *)(a1 + 48), 1, 0xDu, &v33);
        if ( v18 )
        {
          v8 = 0;
          v10 = (unsigned __int64)a2 + a2[10] + 24;
          while ( v8 < a2[3] )
          {
            if ( (unsigned int)(*(_DWORD *)(v18 + 12) - *(_DWORD *)(v10 + 12)) < *(_DWORD *)(v10 + 8) )
            {
              v35 = *(_QWORD *)(a1 + 48) + *(unsigned int *)(v10 + 12);
              v34 = *(unsigned int *)(v10 + 8);
              LdrpMakePermanentImageCommit();
              ZwProtectVirtualMemory(-1, &v35, &v34, 2, &v32);
              break;
            }
            ++v8;
            v10 += 40LL;
          }
        }
      }
    }
    v11 = *(_DWORD *)(a3 + 144);
    if ( (v11 & 0x1000000) != 0 )
    {
      v10 = *(_QWORD *)(a3 + 304);
      v37 = (__int64 (__fastcall **)())v10;
      if ( v10 && (v8 = *(_QWORD *)(a1 + 48), v10 >= v8) && (v8 = *(unsigned int *)(a1 + 64) + v8 - 8, v10 <= v8) )
      {
        Base = v10;
        v39[0] = LdrpCgRoutineCallback;
        v7 = 1;
      }
      else
      {
        v37 = 0;
      }
    }
    v36 = 0;
    v12 = 0;
    if ( (unsigned int)LdrControlFlowGuardEnforced(v8, v10) && (a2[47] & 0x4000) != 0 && (v11 & 0x100) != 0 )
    {
      v13 = *(__int64 (__fastcall ***)())(a3 + 112);
      if ( v13
        && (v19 = *(_QWORD *)(a1 + 48), (unsigned __int64)v13 >= v19)
        && (unsigned __int64)v13 <= *(unsigned int *)(a1 + 64) + v19 - 8 )
      {
        v20 = 2 * v7++;
        v39[v20 - 1] = v13;
        v39[v20] = LdrpCfgCheckRoutineCallback;
      }
      else
      {
        v13 = 0;
      }
      v14 = *(__int64 (__fastcall ***)())(a3 + 120);
      if ( v14
        && (v21 = *(_QWORD *)(a1 + 48), (unsigned __int64)v14 >= v21)
        && (unsigned __int64)v14 <= *(unsigned int *)(a1 + 64) + v21 - 8 )
      {
        if ( v7 >= 6 )
          return 3221225534LL;
        v22 = 2 * v7++;
        v39[v22 - 1] = v14;
        v39[v22] = LdrpCfgDispatchRoutineCallback;
      }
      else
      {
        v14 = 0;
      }
      v9 = *(_DWORD *)a3 < 0x130u;
      v33 = 1;
      if ( !v9 )
      {
        v23 = *(_QWORD *)(a3 + 280);
        v36 = (__int64 (__fastcall **)())v23;
        if ( v23 && (v24 = *(_QWORD *)(a1 + 48), v23 >= v24) && v23 <= *(unsigned int *)(a1 + 64) + v24 - 8 )
        {
          if ( v7 >= 6 )
            return 3221225534LL;
          v25 = 2 * v7++;
          v39[v25 - 1] = v23;
          v39[v25] = LdrpCfgCheckRoutineCallback;
        }
        else
        {
          v36 = 0;
        }
        v12 = *(__int64 (__fastcall ***)())(a3 + 288);
        if ( v12
          && (v26 = *(_QWORD *)(a1 + 48), (unsigned __int64)v12 >= v26)
          && (unsigned __int64)v12 <= *(unsigned int *)(a1 + 64) + v26 - 8 )
        {
          if ( v7 >= 6 )
            return 3221225534LL;
          v27 = 2 * v7++;
          v39[v27 - 1] = v12;
          v39[v27] = LdrpCfgDispatchRoutineCallback;
        }
        else
        {
          v12 = 0;
        }
        v6 = *(__int64 (__fastcall ***)())(a3 + 296);
        if ( v6
          && (v28 = *(_QWORD *)(a1 + 48), (unsigned __int64)v6 >= v28)
          && (unsigned __int64)v6 <= *(unsigned int *)(a1 + 64) + v28 - 8 )
        {
          if ( v7 >= 6 )
            return 3221225534LL;
          v29 = 2 * v7++;
          v39[v29 - 1] = v6;
          v39[v29] = LdrpCfgDispatchRoutineCallback;
        }
        else
        {
          v6 = 0;
        }
      }
    }
    else
    {
      v13 = 0;
      v33 = 0;
      v14 = 0;
    }
    qsort(&Base, v7, 0x10u, LdrpSortLoadConfigFptrs);
    v15 = 0;
    while ( v15 < v7 )
    {
      v34 = 8;
      v35 = v39[2 * v15 - 1];
      result = ZwProtectVirtualMemory(-1, &v35, &v34, 4, &v32);
      if ( (int)result >= 0 )
      {
        do
        {
          ((void (__fastcall *)(_QWORD, _QWORD))v39[2 * v15])(v39[2 * v15 - 1], *(unsigned int *)(a3 + 144));
          ++v15;
        }
        while ( v15 < v7 && v39[2 * v15 - 1] + 8 <= v34 + v35 );
        result = ZwProtectVirtualMemory(-1, &v35, &v34, v32, &v32);
        if ( (int)result >= 0 )
          continue;
      }
      return result;
    }
    if ( !v33 )
      return 0;
    if ( v13 )
    {
      v16 = *v13;
      if ( (*v13 == LdrpValidateUserCallTarget
         || v16 == LdrpValidateUserCallTargetES
         || v16 == (__int64 (__fastcall *)())qword_1801E3550
         || v16 == (__int64 (__fastcall *)())qword_1801E3558)
        && (!v14
         || *v14 == LdrpDispatchUserCallTargetES
         || *v14 == LdrpDispatchUserCallTarget
         || *v14 == (__int64 (__fastcall *)())qword_1801E3560
         || *v14 == (__int64 (__fastcall *)())qword_1801E3568)
        && (!v36 || *v36 == v16)
        && (!v12
         || *v12 == (__int64 (__fastcall *)())qword_1801E3560
         || *v12 == LdrpDispatchUserCallTarget
         || *v12 == LdrpDispatchUserCallTargetES
         || *v12 == (__int64 (__fastcall *)())qword_1801E3568)
        && (!v6
         || *v6 == (__int64 (__fastcall *)())qword_1801E3560
         || *v6 == LdrpDispatchUserCallTarget
         || *v6 == LdrpDispatchUserCallTargetES
         || *v6 == (__int64 (__fastcall *)())qword_1801E3568)
        && (!v37 || *v37 == LdrpCgLogFailure) )
      {
        return 0;
      }
    }
    return 3221225534LL;
  }
  return 0;
}

```

## disassembly

```asm
0x180069678  mov     [rsp-8+arg_18], rbx
0x18006967d  push    rbp
0x18006967e  push    rsi
0x18006967f  push    rdi
0x180069680  push    r12
0x180069682  push    r13
0x180069684  push    r14
0x180069686  push    r15
0x180069688  lea     rbp, [rsp-27h]
0x18006968d  sub     rsp, 0D0h
0x180069694  mov     rax, cs:__security_cookie
0x18006969b  xor     rax, rsp
0x18006969e  mov     [rbp+57h+var_40], rax
0x1800696a2  mov     r13, rdx
0x1800696a5  mov     rsi, r8
0x1800696a8  xor     edx, edx; Val
0x1800696aa  mov     rbx, rcx
0x1800696ad  lea     rcx, [rbp+57h+Base]; void *
0x1800696b1  lea     r8d, [rdx+60h]; Size
0x1800696b5  call    memset$thunk$772440563353939046
0x1800696ba  xor     r15d, r15d
0x1800696bd  mov     [rbp+57h+var_D0], r15d
0x1800696c1  mov     [rbp+57h+var_C0], r15
0x1800696c5  mov     [rbp+57h+var_C8], r15
0x1800696c9  test    rsi, rsi
0x1800696cc  jz      loc_180069800
0x1800696d2  cmp     dword ptr [rsi], 94h
0x1800696d8  jb      loc_180069800
0x1800696de  mov     edx, cs:LdrpPolicyBits
0x1800696e4  mov     r9d, 400h
0x1800696ea  and     edx, 4
0x1800696ed  mov     [rbp+57h+var_B0], r15
0x1800696f1  mov     eax, edx
0x1800696f3  mov     r8d, 7B00h
0x1800696f9  neg     eax
0x1800696fb  mov     r14d, 8000h
0x180069701  movzx   eax, word ptr [rsi+4Eh]
0x180069705  mov     edi, r15d
0x180069708  sbb     ecx, ecx
0x18006970a  and     ecx, r9d
0x18006970d  add     ecx, r8d
0x180069710  or      ecx, r14d
0x180069713  and     ecx, eax
0x180069715  neg     edx
0x180069717  mov     [rbx+118h], ecx
0x18006971d  sbb     eax, eax
0x18006971f  and     eax, r9d
0x180069722  add     eax, r8d
0x180069725  test    ecx, eax
0x180069727  jnz     loc_180069C3E
0x18006972d  test    dword ptr [rsi+90h], 1000h
0x180069737  jnz     loc_1800698DB
0x18006973d  mov     r14d, [rsi+90h]
0x180069744  bt      r14d, 18h
0x180069749  jb      loc_180069B68
0x18006974f  mov     [rbp+57h+var_B8], r15
0x180069753  mov     r12, r15
0x180069756  call    LdrControlFlowGuardEnforced
0x18006975b  test    eax, eax
0x18006975d  jnz     loc_180069983
0x180069763  xor     r14d, r14d
0x180069766  mov     [rbp+57h+var_CC], r12d
0x18006976a  xor     r13d, r13d
0x18006976d  lea     r9, LdrpSortLoadConfigFptrs; CompareFunction
0x180069774  mov     r8d, 10h; SizeOfElements
0x18006977a  mov     rdx, rdi; NumOfElements
0x18006977d  lea     rcx, [rbp+57h+Base]; Base
0x180069781  call    qsort
0x180069786  xor     ebx, ebx
0x180069788  cmp     rbx, rdi
0x18006978b  jb      loc_180069836
0x180069791  cmp     [rbp+57h+var_CC], 0
0x180069795  jz      short loc_180069800
0x180069797  test    r14, r14
0x18006979a  jz      loc_18006982F
0x1800697a0  mov     rax, [r14]
0x1800697a3  lea     rcx, LdrpValidateUserCallTarget
0x1800697aa  cmp     rax, rcx
0x1800697ad  jnz     loc_180069BB5
0x1800697b3  mov     rcx, cs:qword_1801E3568
0x1800697ba  lea     r9, LdrpDispatchUserCallTargetES
0x1800697c1  mov     rdx, cs:qword_1801E3560
0x1800697c8  lea     r10, LdrpDispatchUserCallTarget
0x1800697cf  test    r13, r13
0x1800697d2  jnz     loc_180069C11
0x1800697d8  mov     r8, [rbp+57h+var_B8]
0x1800697dc  test    r8, r8
0x1800697df  jnz     short loc_18006982A
0x1800697e1  test    r12, r12
0x1800697e4  jnz     loc_180069BE4
0x1800697ea  test    r15, r15
0x1800697ed  jnz     loc_180069B3F
0x1800697f3  mov     rax, [rbp+57h+var_B0]
0x1800697f7  test    rax, rax
0x1800697fa  jnz     loc_180069CA4
0x180069800  xor     eax, eax
0x180069802  mov     rcx, [rbp+57h+var_40]
0x180069806  xor     rcx, rsp; StackCookie
0x180069809  call    __security_check_cookie
0x18006980e  mov     rbx, [rsp+100h+arg_18]
0x180069816  add     rsp, 0D0h
0x18006981d  pop     r15
0x18006981f  pop     r14
0x180069821  pop     r13
0x180069823  pop     r12
0x180069825  pop     rdi
0x180069826  pop     rsi
0x180069827  pop     rbp
0x180069828  retn
0x18006982a  cmp     [r8], rax
0x18006982d  jz      short loc_1800697E1
0x18006982f  mov     eax, 0C000003Eh
0x180069834  jmp     short loc_180069802
0x180069836  mov     rax, rbx
0x180069839  mov     [rbp+57h+var_C8], 8
0x180069841  add     rax, rax
0x180069844  lea     r8, [rbp+57h+var_C8]
0x180069848  mov     r9d, 4
0x18006984e  lea     rdx, [rbp+57h+var_C0]
0x180069852  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180069856  mov     rax, [rbp+rax*8+57h+Base]
0x18006985b  mov     [rbp+57h+var_C0], rax
0x18006985f  lea     rax, [rbp+57h+var_D0]
0x180069863  mov     [rsp+100h+var_E0], rax
0x180069868  call    ZwProtectVirtualMemory
0x18006986d  test    eax, eax
0x18006986f  js      short loc_180069802
0x180069871  mov     edx, [rsi+90h]
0x180069877  mov     rax, rbx
0x18006987a  add     rax, rax
0x18006987d  mov     rcx, [rbp+rax*8+57h+Base]
0x180069882  mov     rax, [rbp+rax*8+57h+var_98]
0x180069887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006988c  inc     rbx
0x18006988f  cmp     rbx, rdi
0x180069892  jnb     short loc_1800698B0
0x180069894  mov     rcx, [rbp+57h+var_C0]
0x180069898  mov     rax, rbx
0x18006989b  add     rcx, [rbp+57h+var_C8]
0x18006989f  add     rax, rax
0x1800698a2  mov     rdx, [rbp+rax*8+57h+Base]
0x1800698a7  add     rdx, 8
0x1800698ab  cmp     rdx, rcx
0x1800698ae  jbe     short loc_180069871
0x1800698b0  mov     r9d, [rbp+57h+var_D0]
0x1800698b4  lea     rax, [rbp+57h+var_D0]
0x1800698b8  lea     r8, [rbp+57h+var_C8]
0x1800698bc  mov     [rsp+100h+var_E0], rax
0x1800698c1  lea     rdx, [rbp+57h+var_C0]
0x1800698c5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800698c9  call    ZwProtectVirtualMemory
0x1800698ce  test    eax, eax
0x1800698d0  jns     loc_180069788
0x1800698d6  jmp     loc_180069802
0x1800698db  mov     eax, [rbx+68h]
0x1800698de  or      eax, r14d
0x1800698e1  mov     [rbx+68h], eax
0x1800698e4  test    dword ptr [rsi+90h], 2000h
0x1800698ee  jz      loc_18006973D
0x1800698f4  mov     rcx, [rbx+30h]
0x1800698f8  lea     r9, [rbp+57h+var_CC]
0x1800698fc  mov     r8d, 0Dh
0x180069902  mov     dl, 1
0x180069904  call    RtlImageDirectoryEntryToData
0x180069909  mov     r8, rax
0x18006990c  test    rax, rax
0x18006990f  jz      loc_18006973D
0x180069915  movzx   edx, word ptr [r13+14h]
0x18006991a  mov     rcx, r15
0x18006991d  movzx   r9d, word ptr [r13+6]
0x180069922  add     rdx, 18h
0x180069926  add     rdx, r13
0x180069929  cmp     rcx, r9
0x18006992c  jnb     loc_18006973D
0x180069932  mov     eax, [r8+0Ch]
0x180069936  sub     eax, [rdx+0Ch]
0x180069939  cmp     eax, [rdx+8]
0x18006993c  jb      short loc_180069947
0x18006993e  inc     rcx
0x180069941  add     rdx, 28h ; '('
0x180069945  jmp     short loc_180069929
0x180069947  mov     ecx, [rdx+0Ch]
0x18006994a  add     rcx, [rbx+30h]
0x18006994e  mov     [rbp+57h+var_C0], rcx
0x180069952  mov     edx, [rdx+8]
0x180069955  mov     [rbp+57h+var_C8], rdx
0x180069959  call    LdrpMakePermanentImageCommit
0x18006995e  lea     rdx, [rbp+57h+var_D0]
0x180069962  mov     r9d, 2
0x180069968  mov     [rsp+100h+var_E0], rdx
0x18006996d  lea     r8, [rbp+57h+var_C8]
0x180069971  lea     rdx, [rbp+57h+var_C0]
0x180069975  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180069979  call    ZwProtectVirtualMemory
0x18006997e  jmp     loc_18006973D
0x180069983  movzx   eax, word ptr [r13+5Eh]
0x180069988  mov     ecx, 0Eh
0x18006998d  bt      ax, cx
0x180069991  setb    cl
0x180069994  bt      r14d, 8
0x180069999  setb    al
0x18006999c  test    al, cl
0x18006999e  jz      loc_180069763
0x1800699a4  mov     r14, [rsi+70h]
0x1800699a8  lea     r8, LdrpCfgCheckRoutineCallback
0x1800699af  test    r14, r14
0x1800699b2  jz      loc_180069C6C
0x1800699b8  mov     rcx, [rbx+30h]
0x1800699bc  cmp     r14, rcx
0x1800699bf  jb      loc_180069C6C
0x1800699c5  mov     eax, [rbx+40h]
0x1800699c8  add     rcx, 0FFFFFFFFFFFFFFF8h
0x1800699cc  add     rcx, rax
0x1800699cf  cmp     r14, rcx
0x1800699d2  ja      loc_180069C6C
0x1800699d8  mov     rax, rdi
0x1800699db  add     rax, rax
0x1800699de  inc     rdi
0x1800699e1  mov     [rbp+rax*8+57h+Base], r14
0x1800699e6  mov     [rbp+rax*8+57h+var_98], r8
0x1800699eb  mov     r13, [rsi+78h]
0x1800699ef  lea     r9, LdrpCfgDispatchRoutineCallback
0x1800699f6  test    r13, r13
0x1800699f9  jz      loc_180069C74
0x1800699ff  mov     rcx, [rbx+30h]
0x180069a03  cmp     r13, rcx
0x180069a06  jb      loc_180069C74
0x180069a0c  mov     eax, [rbx+40h]
0x180069a0f  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180069a13  add     rcx, rax
0x180069a16  cmp     r13, rcx
0x180069a19  ja      loc_180069C74
0x180069a1f  cmp     rdi, 6
0x180069a23  jnb     loc_18006982F
0x180069a29  mov     rax, rdi
0x180069a2c  add     rax, rax
0x180069a2f  inc     rdi
0x180069a32  mov     [rbp+rax*8+57h+Base], r13
0x180069a37  mov     [rbp+rax*8+57h+var_98], r9
0x180069a3c  cmp     dword ptr [rsi], 130h
0x180069a42  mov     [rbp+57h+var_CC], 1
0x180069a49  jb      loc_18006976D
0x180069a4f  mov     rdx, [rsi+118h]
0x180069a56  mov     [rbp+57h+var_B8], rdx
0x180069a5a  test    rdx, rdx
0x180069a5d  jz      loc_180069C7C
0x180069a63  mov     rcx, [rbx+30h]
0x180069a67  cmp     rdx, rcx
0x180069a6a  jb      loc_180069C7C
0x180069a70  mov     eax, [rbx+40h]
0x180069a73  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180069a77  add     rcx, rax
0x180069a7a  cmp     rdx, rcx
0x180069a7d  ja      loc_180069C7C
0x180069a83  cmp     rdi, 6
0x180069a87  jnb     loc_18006982F
0x180069a8d  mov     rax, rdi
0x180069a90  add     rax, rax
0x180069a93  inc     rdi
0x180069a96  mov     [rbp+rax*8+57h+Base], rdx
0x180069a9b  mov     [rbp+rax*8+57h+var_98], r8
0x180069aa0  mov     r12, [rsi+120h]
0x180069aa7  test    r12, r12
0x180069aaa  jz      loc_180069C85
0x180069ab0  mov     rcx, [rbx+30h]
0x180069ab4  cmp     r12, rcx
0x180069ab7  jb      loc_180069C85
0x180069abd  mov     eax, [rbx+40h]
0x180069ac0  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180069ac4  add     rcx, rax
0x180069ac7  cmp     r12, rcx
0x180069aca  ja      loc_180069C85
0x180069ad0  cmp     rdi, 6
0x180069ad4  jnb     loc_18006982F
0x180069ada  mov     rax, rdi
0x180069add  add     rax, rax
0x180069ae0  inc     rdi
0x180069ae3  mov     [rbp+rax*8+57h+Base], r12
0x180069ae8  mov     [rbp+rax*8+57h+var_98], r9
0x180069aed  mov     r15, [rsi+128h]
0x180069af4  test    r15, r15
0x180069af7  jz      loc_180069C8D
0x180069afd  mov     rcx, [rbx+30h]
0x180069b01  cmp     r15, rcx
0x180069b04  jb      loc_180069C8D
0x180069b0a  mov     eax, [rbx+40h]
0x180069b0d  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180069b11  add     rcx, rax
0x180069b14  cmp     r15, rcx
0x180069b17  ja      loc_180069C8D
0x180069b1d  cmp     rdi, 6
0x180069b21  jnb     loc_18006982F
0x180069b27  mov     rax, rdi
0x180069b2a  add     rax, rax
0x180069b2d  inc     rdi
0x180069b30  mov     [rbp+rax*8+57h+Base], r15
0x180069b35  mov     [rbp+rax*8+57h+var_98], r9
0x180069b3a  jmp     loc_18006976D
0x180069b3f  cmp     [r15], rdx
0x180069b42  jz      loc_1800697F3
  ... truncated ...
```
