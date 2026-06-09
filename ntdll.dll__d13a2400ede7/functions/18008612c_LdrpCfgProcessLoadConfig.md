# LdrpCfgProcessLoadConfig

- ea: `0x18008612c`
- end: `0x18008676d`
- name: `LdrpCfgProcessLoadConfig`
- size: `1601`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180085e5c`
- `0x1801379c4`

## callees

- `0x180082a00`
- `0x1800836d0`
- `0x1800858c4`
- `0x18008612c`
- `0x1800e78c4`
- `0x18012b760`
- `0x18015f4e0`
- `0x180162810`
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
0x18008612c  mov     [rsp-8+arg_18], rbx
0x180086131  push    rbp
0x180086132  push    rsi
0x180086133  push    rdi
0x180086134  push    r12
0x180086136  push    r13
0x180086138  push    r14
0x18008613a  push    r15
0x18008613c  lea     rbp, [rsp-27h]
0x180086141  sub     rsp, 0D0h
0x180086148  mov     rax, cs:__security_cookie
0x18008614f  xor     rax, rsp
0x180086152  mov     [rbp+57h+var_40], rax
0x180086156  mov     r13, rdx
0x180086159  mov     rsi, r8
0x18008615c  xor     edx, edx; Val
0x18008615e  mov     rbx, rcx
0x180086161  lea     rcx, [rbp+57h+Base]; void *
0x180086165  lea     r8d, [rdx+60h]; Size
0x180086169  call    memset$thunk$772440563353939046
0x18008616e  xor     r15d, r15d
0x180086171  mov     [rbp+57h+var_D0], r15d
0x180086175  mov     [rbp+57h+var_C0], r15
0x180086179  mov     [rbp+57h+var_C8], r15
0x18008617d  test    rsi, rsi
0x180086180  jz      loc_1800862B4
0x180086186  cmp     dword ptr [rsi], 94h
0x18008618c  jb      loc_1800862B4
0x180086192  mov     edx, cs:LdrpPolicyBits
0x180086198  mov     r9d, 400h
0x18008619e  and     edx, 4
0x1800861a1  mov     [rbp+57h+var_B0], r15
0x1800861a5  mov     eax, edx
0x1800861a7  mov     r8d, 7B00h
0x1800861ad  neg     eax
0x1800861af  mov     r14d, 8000h
0x1800861b5  movzx   eax, word ptr [rsi+4Eh]
0x1800861b9  mov     edi, r15d
0x1800861bc  sbb     ecx, ecx
0x1800861be  and     ecx, r9d
0x1800861c1  add     ecx, r8d
0x1800861c4  or      ecx, r14d
0x1800861c7  and     ecx, eax
0x1800861c9  neg     edx
0x1800861cb  mov     [rbx+118h], ecx
0x1800861d1  sbb     eax, eax
0x1800861d3  and     eax, r9d
0x1800861d6  add     eax, r8d
0x1800861d9  test    ecx, eax
0x1800861db  jnz     loc_1800866F2
0x1800861e1  test    dword ptr [rsi+90h], 1000h
0x1800861eb  jnz     loc_18008638F
0x1800861f1  mov     r14d, [rsi+90h]
0x1800861f8  bt      r14d, 18h
0x1800861fd  jb      loc_18008661C
0x180086203  mov     [rbp+57h+var_B8], r15
0x180086207  mov     r12, r15
0x18008620a  call    LdrControlFlowGuardEnforced
0x18008620f  test    eax, eax
0x180086211  jnz     loc_180086437
0x180086217  xor     r14d, r14d
0x18008621a  mov     [rbp+57h+var_CC], r12d
0x18008621e  xor     r13d, r13d
0x180086221  lea     r9, LdrpSortLoadConfigFptrs; CompareFunction
0x180086228  mov     r8d, 10h; SizeOfElements
0x18008622e  mov     rdx, rdi; NumOfElements
0x180086231  lea     rcx, [rbp+57h+Base]; Base
0x180086235  call    qsort
0x18008623a  xor     ebx, ebx
0x18008623c  cmp     rbx, rdi
0x18008623f  jb      loc_1800862EA
0x180086245  cmp     [rbp+57h+var_CC], 0
0x180086249  jz      short loc_1800862B4
0x18008624b  test    r14, r14
0x18008624e  jz      loc_1800862E3
0x180086254  mov     rax, [r14]
0x180086257  lea     rcx, LdrpValidateUserCallTarget
0x18008625e  cmp     rax, rcx
0x180086261  jnz     loc_180086669
0x180086267  mov     rcx, cs:qword_1801E3568
0x18008626e  lea     r9, LdrpDispatchUserCallTargetES
0x180086275  mov     rdx, cs:qword_1801E3560
0x18008627c  lea     r10, LdrpDispatchUserCallTarget
0x180086283  test    r13, r13
0x180086286  jnz     loc_1800866C5
0x18008628c  mov     r8, [rbp+57h+var_B8]
0x180086290  test    r8, r8
0x180086293  jnz     short loc_1800862DE
0x180086295  test    r12, r12
0x180086298  jnz     loc_180086698
0x18008629e  test    r15, r15
0x1800862a1  jnz     loc_1800865F3
0x1800862a7  mov     rax, [rbp+57h+var_B0]
0x1800862ab  test    rax, rax
0x1800862ae  jnz     loc_180086758
0x1800862b4  xor     eax, eax
0x1800862b6  mov     rcx, [rbp+57h+var_40]
0x1800862ba  xor     rcx, rsp; StackCookie
0x1800862bd  call    __security_check_cookie
0x1800862c2  mov     rbx, [rsp+100h+arg_18]
0x1800862ca  add     rsp, 0D0h
0x1800862d1  pop     r15
0x1800862d3  pop     r14
0x1800862d5  pop     r13
0x1800862d7  pop     r12
0x1800862d9  pop     rdi
0x1800862da  pop     rsi
0x1800862db  pop     rbp
0x1800862dc  retn
0x1800862de  cmp     [r8], rax
0x1800862e1  jz      short loc_180086295
0x1800862e3  mov     eax, 0C000003Eh
0x1800862e8  jmp     short loc_1800862B6
0x1800862ea  mov     rax, rbx
0x1800862ed  mov     [rbp+57h+var_C8], 8
0x1800862f5  add     rax, rax
0x1800862f8  lea     r8, [rbp+57h+var_C8]
0x1800862fc  mov     r9d, 4
0x180086302  lea     rdx, [rbp+57h+var_C0]
0x180086306  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008630a  mov     rax, [rbp+rax*8+57h+Base]
0x18008630f  mov     [rbp+57h+var_C0], rax
0x180086313  lea     rax, [rbp+57h+var_D0]
0x180086317  mov     [rsp+100h+var_E0], rax
0x18008631c  call    ZwProtectVirtualMemory
0x180086321  test    eax, eax
0x180086323  js      short loc_1800862B6
0x180086325  mov     edx, [rsi+90h]
0x18008632b  mov     rax, rbx
0x18008632e  add     rax, rax
0x180086331  mov     rcx, [rbp+rax*8+57h+Base]
0x180086336  mov     rax, [rbp+rax*8+57h+var_98]
0x18008633b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086340  inc     rbx
0x180086343  cmp     rbx, rdi
0x180086346  jnb     short loc_180086364
0x180086348  mov     rcx, [rbp+57h+var_C0]
0x18008634c  mov     rax, rbx
0x18008634f  add     rcx, [rbp+57h+var_C8]
0x180086353  add     rax, rax
0x180086356  mov     rdx, [rbp+rax*8+57h+Base]
0x18008635b  add     rdx, 8
0x18008635f  cmp     rdx, rcx
0x180086362  jbe     short loc_180086325
0x180086364  mov     r9d, [rbp+57h+var_D0]
0x180086368  lea     rax, [rbp+57h+var_D0]
0x18008636c  lea     r8, [rbp+57h+var_C8]
0x180086370  mov     [rsp+100h+var_E0], rax
0x180086375  lea     rdx, [rbp+57h+var_C0]
0x180086379  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008637d  call    ZwProtectVirtualMemory
0x180086382  test    eax, eax
0x180086384  jns     loc_18008623C
0x18008638a  jmp     loc_1800862B6
0x18008638f  mov     eax, [rbx+68h]
0x180086392  or      eax, r14d
0x180086395  mov     [rbx+68h], eax
0x180086398  test    dword ptr [rsi+90h], 2000h
0x1800863a2  jz      loc_1800861F1
0x1800863a8  mov     rcx, [rbx+30h]
0x1800863ac  lea     r9, [rbp+57h+var_CC]
0x1800863b0  mov     r8d, 0Dh
0x1800863b6  mov     dl, 1
0x1800863b8  call    RtlImageDirectoryEntryToData
0x1800863bd  mov     r8, rax
0x1800863c0  test    rax, rax
0x1800863c3  jz      loc_1800861F1
0x1800863c9  movzx   edx, word ptr [r13+14h]
0x1800863ce  mov     rcx, r15
0x1800863d1  movzx   r9d, word ptr [r13+6]
0x1800863d6  add     rdx, 18h
0x1800863da  add     rdx, r13
0x1800863dd  cmp     rcx, r9
0x1800863e0  jnb     loc_1800861F1
0x1800863e6  mov     eax, [r8+0Ch]
0x1800863ea  sub     eax, [rdx+0Ch]
0x1800863ed  cmp     eax, [rdx+8]
0x1800863f0  jb      short loc_1800863FB
0x1800863f2  inc     rcx
0x1800863f5  add     rdx, 28h ; '('
0x1800863f9  jmp     short loc_1800863DD
0x1800863fb  mov     ecx, [rdx+0Ch]
0x1800863fe  add     rcx, [rbx+30h]
0x180086402  mov     [rbp+57h+var_C0], rcx
0x180086406  mov     edx, [rdx+8]
0x180086409  mov     [rbp+57h+var_C8], rdx
0x18008640d  call    LdrpMakePermanentImageCommit
0x180086412  lea     rdx, [rbp+57h+var_D0]
0x180086416  mov     r9d, 2
0x18008641c  mov     [rsp+100h+var_E0], rdx
0x180086421  lea     r8, [rbp+57h+var_C8]
0x180086425  lea     rdx, [rbp+57h+var_C0]
0x180086429  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008642d  call    ZwProtectVirtualMemory
0x180086432  jmp     loc_1800861F1
0x180086437  movzx   eax, word ptr [r13+5Eh]
0x18008643c  mov     ecx, 0Eh
0x180086441  bt      ax, cx
0x180086445  setb    cl
0x180086448  bt      r14d, 8
0x18008644d  setb    al
0x180086450  test    al, cl
0x180086452  jz      loc_180086217
0x180086458  mov     r14, [rsi+70h]
0x18008645c  lea     r8, LdrpCfgCheckRoutineCallback
0x180086463  test    r14, r14
0x180086466  jz      loc_180086720
0x18008646c  mov     rcx, [rbx+30h]
0x180086470  cmp     r14, rcx
0x180086473  jb      loc_180086720
0x180086479  mov     eax, [rbx+40h]
0x18008647c  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180086480  add     rcx, rax
0x180086483  cmp     r14, rcx
0x180086486  ja      loc_180086720
0x18008648c  mov     rax, rdi
0x18008648f  add     rax, rax
0x180086492  inc     rdi
0x180086495  mov     [rbp+rax*8+57h+Base], r14
0x18008649a  mov     [rbp+rax*8+57h+var_98], r8
0x18008649f  mov     r13, [rsi+78h]
0x1800864a3  lea     r9, LdrpCfgDispatchRoutineCallback
0x1800864aa  test    r13, r13
0x1800864ad  jz      loc_180086728
0x1800864b3  mov     rcx, [rbx+30h]
0x1800864b7  cmp     r13, rcx
0x1800864ba  jb      loc_180086728
0x1800864c0  mov     eax, [rbx+40h]
0x1800864c3  add     rcx, 0FFFFFFFFFFFFFFF8h
0x1800864c7  add     rcx, rax
0x1800864ca  cmp     r13, rcx
0x1800864cd  ja      loc_180086728
0x1800864d3  cmp     rdi, 6
0x1800864d7  jnb     loc_1800862E3
0x1800864dd  mov     rax, rdi
0x1800864e0  add     rax, rax
0x1800864e3  inc     rdi
0x1800864e6  mov     [rbp+rax*8+57h+Base], r13
0x1800864eb  mov     [rbp+rax*8+57h+var_98], r9
0x1800864f0  cmp     dword ptr [rsi], 130h
0x1800864f6  mov     [rbp+57h+var_CC], 1
0x1800864fd  jb      loc_180086221
0x180086503  mov     rdx, [rsi+118h]
0x18008650a  mov     [rbp+57h+var_B8], rdx
0x18008650e  test    rdx, rdx
0x180086511  jz      loc_180086730
0x180086517  mov     rcx, [rbx+30h]
0x18008651b  cmp     rdx, rcx
0x18008651e  jb      loc_180086730
0x180086524  mov     eax, [rbx+40h]
0x180086527  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18008652b  add     rcx, rax
0x18008652e  cmp     rdx, rcx
0x180086531  ja      loc_180086730
0x180086537  cmp     rdi, 6
0x18008653b  jnb     loc_1800862E3
0x180086541  mov     rax, rdi
0x180086544  add     rax, rax
0x180086547  inc     rdi
0x18008654a  mov     [rbp+rax*8+57h+Base], rdx
0x18008654f  mov     [rbp+rax*8+57h+var_98], r8
0x180086554  mov     r12, [rsi+120h]
0x18008655b  test    r12, r12
0x18008655e  jz      loc_180086739
0x180086564  mov     rcx, [rbx+30h]
0x180086568  cmp     r12, rcx
0x18008656b  jb      loc_180086739
0x180086571  mov     eax, [rbx+40h]
0x180086574  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180086578  add     rcx, rax
0x18008657b  cmp     r12, rcx
0x18008657e  ja      loc_180086739
0x180086584  cmp     rdi, 6
0x180086588  jnb     loc_1800862E3
0x18008658e  mov     rax, rdi
0x180086591  add     rax, rax
0x180086594  inc     rdi
0x180086597  mov     [rbp+rax*8+57h+Base], r12
0x18008659c  mov     [rbp+rax*8+57h+var_98], r9
0x1800865a1  mov     r15, [rsi+128h]
0x1800865a8  test    r15, r15
0x1800865ab  jz      loc_180086741
0x1800865b1  mov     rcx, [rbx+30h]
0x1800865b5  cmp     r15, rcx
0x1800865b8  jb      loc_180086741
0x1800865be  mov     eax, [rbx+40h]
0x1800865c1  add     rcx, 0FFFFFFFFFFFFFFF8h
0x1800865c5  add     rcx, rax
0x1800865c8  cmp     r15, rcx
0x1800865cb  ja      loc_180086741
0x1800865d1  cmp     rdi, 6
0x1800865d5  jnb     loc_1800862E3
0x1800865db  mov     rax, rdi
0x1800865de  add     rax, rax
0x1800865e1  inc     rdi
0x1800865e4  mov     [rbp+rax*8+57h+Base], r15
0x1800865e9  mov     [rbp+rax*8+57h+var_98], r9
0x1800865ee  jmp     loc_180086221
0x1800865f3  cmp     [r15], rdx
0x1800865f6  jz      loc_1800862A7
  ... truncated ...
```
