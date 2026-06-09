# IP_RESTRICTION_LIST::Check(int,sockaddr *,STRU &,void (*)(void *),void *,IHttpContext *,int *,int *,int *)

- ea: `0x18000369c`
- end: `0x180003c0f`
- name: `?Check@IP_RESTRICTION_LIST@@QEAAJHPEAUsockaddr@@AEAVSTRU@@P6AXPEAX@Z2PEAVIHttpContext@@PEAH55@Z`
- size: `1395`
- prototype: `__int64 __fastcall(IP_RESTRICTION_LIST *this, __int64, struct sockaddr *, struct STRU *, void (*)(void *), void *, struct IHttpContext *, int *, int *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001b5c`

## callees

- `0x18000369c`
- `0x180003c18`
- `0x180003f28`
- `0x18000401c`
- `0x180004110`
- `0x180004ad0`
- `0x180005010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003945`
- `msvcrt!_wcsicmp` at `0x180003945`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003bd6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003be0`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003bd6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003be0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003a1c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003b80`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003b97`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003a1c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003b80`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003b97`

## pseudocode

```c
__int64 __fastcall IP_RESTRICTION_LIST::Check(
        IP_RESTRICTION_LIST *this,
        __int64 a2,
        struct sockaddr *a3,
        struct STRU *a4,
        void (*a5)(void *),
        void *a6,
        struct IHttpContext *a7,
        int *a8,
        int *a9,
        int *a10)
{
  int *v11; // r8
  __int64 v13; // rax
  unsigned int v14; // eax
  unsigned __int64 v15; // rbx
  ADDRESS_FAMILY sa_family; // dx
  bool v17; // al
  bool v18; // al
  __int16 v19; // cx
  bool v20; // al
  bool v21; // zf
  unsigned int v22; // edx
  __int16 v23; // di
  __int64 v24; // rcx
  __int64 result; // rax
  int v26; // eax
  __int64 v27; // rax
  const wchar_t *v28; // rdx
  const wchar_t *v29; // rcx
  int (__fastcall ***v30)(_QWORD, GUID **); // rax
  int *v31; // rdx
  int v32; // eax
  int (__fastcall ***v33)(_QWORD, GUID **); // rax
  const unsigned __int16 *v34; // rbx
  struct IHttpTraceContext *v35; // rax
  const struct _GUID *v36; // rdx
  int v37; // eax
  int (__fastcall ***v38)(_QWORD, GUID **); // rax
  IP_RESTRICTION_LIST *v39; // rcx
  unsigned __int16 *v40; // rbx
  struct IHttpTraceContext *v41; // rax
  const struct _GUID *v42; // rdx
  void *v43; // [rsp+20h] [rbp-C9h]
  unsigned int v44; // [rsp+40h] [rbp-A9h] BYREF
  int v45; // [rsp+44h] [rbp-A5h] BYREF
  GUID *v46; // [rsp+48h] [rbp-A1h] BYREF
  __int128 v47; // [rsp+50h] [rbp-99h]
  void (*v48)(void *); // [rsp+60h] [rbp-89h]
  int *v49; // [rsp+68h] [rbp-81h]
  _BYTE v50[32]; // [rsp+70h] [rbp-79h] BYREF
  unsigned __int16 *v51; // [rsp+90h] [rbp-59h]
  _BYTE v52[56]; // [rsp+A8h] [rbp-41h] BYREF

  v11 = a8;
  v49 = a8;
  v48 = (void (*)(void *))a4;
  if ( *((_DWORD *)this + 1) )
  {
    v13 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a7 + 32LL))(a7);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 112LL))(v13, 12);
    a4 = (struct STRU *)v48;
    v11 = v49;
  }
  v14 = 0;
  v44 = 0;
  if ( *((_DWORD *)this + 1) )
  {
    while ( 1 )
    {
      v15 = *((_QWORD *)this + 1) + ((unsigned __int64)v14 << 8);
      if ( !*(_DWORD *)(v15 + 64) )
        goto LABEL_63;
      sa_family = a3->sa_family;
      if ( a3->sa_family == 23 )
        v17 = !*(_WORD *)&a3->sa_data[6]
           && !*(_WORD *)&a3->sa_data[8]
           && !*(_WORD *)&a3->sa_data[10]
           && !*(_WORD *)&a3->sa_data[12]
           && !a3[1].sa_family
           && !*(_WORD *)a3[1].sa_data
           && !*(_WORD *)&a3[1].sa_data[2]
           && *(_WORD *)&a3[1].sa_data[4] == 256;
      else
        v17 = a3->sa_data[2] == 127;
      if ( v17 )
      {
        if ( *(_WORD *)(v15 + 4) == 23 )
          v18 = !*(_WORD *)(v15 + 12)
             && !*(_WORD *)(v15 + 14)
             && !*(_WORD *)(v15 + 16)
             && !*(_WORD *)(v15 + 18)
             && !*(_WORD *)(v15 + 20)
             && !*(_WORD *)(v15 + 22)
             && !*(_WORD *)(v15 + 24)
             && *(_WORD *)(v15 + 26) == 256;
        else
          v18 = *(_BYTE *)(v15 + 8) == 127;
        if ( v18 )
        {
LABEL_79:
          *a9 = *(_DWORD *)v15;
          if ( *a9 != 1 )
          {
            v30 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a7 + 272LL))(a7);
            v46 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
            v47 = 0;
            if ( (**v30)(v30, &v46) >= 0 && DWORD2(v47) && DWORD1(v47) >= 3 && ((_DWORD)v47 == 4 || (v47 & 4) != 0) )
            {
              LOWORD(v45) = 0;
              STRU::STRU((STRU *)v50, (unsigned __int16 *)&v45, 1u);
              v31 = (int *)&v44;
              LOWORD(v44) = 0;
              goto LABEL_101;
            }
          }
          return 0;
        }
      }
      v19 = *(_WORD *)(v15 + 4);
      if ( v19 == 23 )
        v20 = !*(_WORD *)(v15 + 12)
           && !*(_WORD *)(v15 + 14)
           && !*(_WORD *)(v15 + 16)
           && !*(_WORD *)(v15 + 18)
           && !*(_WORD *)(v15 + 20)
           && !*(_WORD *)(v15 + 22)
           && !*(_WORD *)(v15 + 24)
           && !*(_WORD *)(v15 + 26);
      else
        v20 = *(_DWORD *)(v15 + 8) == 0;
      if ( v20 )
      {
        v21 = v19 == (__int16)sa_family;
      }
      else
      {
        if ( sa_family != v19 )
          goto LABEL_63;
        if ( *(_DWORD *)(v15 + 60) )
        {
          if ( sa_family == 23 )
          {
            if ( v19 != 23
              || *(_DWORD *)&a3[1].sa_data[6] != *(_DWORD *)(v15 + 28)
              || *(_QWORD *)&a3[1].sa_family != *(_QWORD *)(v15 + 20) )
            {
              goto LABEL_63;
            }
            v21 = *(_QWORD *)&a3->sa_data[6] == *(_QWORD *)(v15 + 12);
          }
          else
          {
            if ( v19 != 2 )
              goto LABEL_63;
            v21 = *(_DWORD *)&a3->sa_data[2] == *(_DWORD *)(v15 + 8);
          }
        }
        else
        {
          if ( sa_family != *(_WORD *)(v15 + 32) )
            goto LABEL_63;
          if ( sa_family != 2 )
          {
            if ( sa_family == 23 )
            {
              v22 = 0;
              while ( (*(_WORD *)&a3->sa_data[2 * v22 + 6] & *(_WORD *)(v15 + 2LL * v22 + 40)) == *(_WORD *)(v15 + 2LL * v22 + 12) )
              {
                v21 = ++v22 == 8;
                if ( v22 >= 8 )
                  goto LABEL_62;
              }
            }
            goto LABEL_63;
          }
          v21 = (*(_DWORD *)(v15 + 36) & *(_DWORD *)&a3->sa_data[2]) == *(_DWORD *)(v15 + 8);
        }
      }
LABEL_62:
      if ( v21 )
        goto LABEL_79;
LABEL_63:
      if ( !*(_DWORD *)(v15 + 120) )
        goto LABEL_77;
      v23 = **(_WORD **)(v15 + 104);
      if ( v23 == 42 && *(_DWORD *)(v15 + 120) == 1 )
      {
LABEL_86:
        v32 = *(_DWORD *)v15;
        *a10 = *(_DWORD *)v15;
        if ( !v32 )
        {
          v33 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a7 + 272LL))(a7);
          v46 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
          v47 = 0;
          if ( (**v33)(v33, &v46) >= 0 && DWORD2(v47) && DWORD1(v47) >= 3 && ((_DWORD)v47 == 4 || (v47 & 4) != 0) )
          {
            v34 = (const unsigned __int16 *)*((_QWORD *)v48 + 4);
            v35 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a7 + 272LL))(a7);
            IISSecurityEvents::SECURITY_REJECTED_HOSTNAME::RaiseEvent(v35, v36, v34);
          }
        }
        return 0;
      }
      v24 = *((unsigned int *)a4 + 12);
      if ( !(_DWORD)v24 )
      {
        v45 = 0;
        result = IP_RESTRICTION_LIST::ReverseDNSLookup(0, a3, 1, (void (*)(void *))a4, v43, a4, &v45, v11);
        if ( (int)result < 0 )
          return result;
        if ( *v49 )
          return 0;
        a4 = (struct STRU *)v48;
        v24 = *((unsigned int *)v48 + 12);
      }
      v26 = *(_DWORD *)(v15 + 120);
      if ( v23 == 42 )
      {
        v27 = (unsigned int)(v26 - 1);
        if ( (unsigned int)v27 > (unsigned int)v24 )
          goto LABEL_77;
        v28 = (const wchar_t *)(*((_QWORD *)a4 + 4) + 2 * (v24 - v27));
        v29 = (const wchar_t *)(*(_QWORD *)(v15 + 104) + 2LL);
      }
      else
      {
        if ( v26 != (_DWORD)v24 )
          goto LABEL_77;
        v28 = (const wchar_t *)*((_QWORD *)a4 + 4);
        v29 = *(const wchar_t **)(v15 + 104);
      }
      if ( !_wcsicmp(v29, v28) )
        goto LABEL_86;
LABEL_77:
      v14 = v44 + 1;
      v44 = v14;
      if ( v14 >= *((_DWORD *)this + 1) )
        break;
      a4 = (struct STRU *)v48;
      v11 = v49;
    }
  }
  v37 = *((_DWORD *)this + 4);
  *v49 = 0;
  if ( v37 )
  {
    *a9 = 1;
    *a10 = 1;
  }
  else
  {
    *a9 = 0;
    *a10 = 0;
    v38 = (int (__fastcall ***)(_QWORD, GUID **))(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a7 + 272LL))(a7);
    v46 = &`WWWServerTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
    v47 = 0;
    if ( (**v38)(v38, &v46) >= 0 && DWORD2(v47) && DWORD1(v47) >= 3 && ((_DWORD)v47 == 4 || (v47 & 4) != 0) )
    {
      LOWORD(v44) = 0;
      STRU::STRU((STRU *)v50, (unsigned __int16 *)&v44, 1u);
      v31 = &v45;
      LOWORD(v45) = 0;
LABEL_101:
      STRU::STRU((STRU *)v52, (unsigned __int16 *)v31, 1u);
      if ( IP_RESTRICTION_LIST::ConvertSockAddrToString(v39, a3, (struct STRU *)v50, (struct STRU *)v52) >= 0 )
      {
        v40 = v51;
        v41 = (struct IHttpTraceContext *)(*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a7 + 272LL))(a7);
        IISSecurityEvents::SECURITY_REJECTED_IP::RaiseEvent(v41, v42, v40);
      }
      STRU::~STRU((STRU *)v52);
      STRU::~STRU((STRU *)v50);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000369c  mov     [rsp-8+arg_8], rbx
0x1800036a1  push    rbp
0x1800036a2  push    rsi
0x1800036a3  push    rdi
0x1800036a4  push    r12
0x1800036a6  push    r13
0x1800036a8  push    r14
0x1800036aa  push    r15
0x1800036ac  lea     rbp, [rsp-7]
0x1800036b1  sub     rsp, 0F0h
0x1800036b8  mov     rax, cs:__security_cookie
0x1800036bf  xor     rax, rsp
0x1800036c2  mov     [rbp+37h+var_40], rax
0x1800036c6  mov     r14, [rbp+37h+arg_30]
0x1800036ca  mov     rsi, r8
0x1800036cd  mov     r8, [rbp+37h+arg_38]
0x1800036d1  xor     edi, edi
0x1800036d3  mov     r13, rcx
0x1800036d6  mov     r15, [rbp+37h+arg_40]
0x1800036dd  mov     r12, [rbp+37h+arg_48]
0x1800036e4  mov     [rsp+120h+var_B8], r8
0x1800036e9  mov     [rsp+120h+var_C0], r9
0x1800036ee  cmp     [rcx+4], edi
0x1800036f1  jbe     short loc_180003721
0x1800036f3  mov     rax, [r14]
0x1800036f6  mov     rcx, r14
0x1800036f9  mov     rax, [rax+20h]
0x1800036fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003702  mov     r8, rax
0x180003705  lea     edx, [rdi+0Ch]
0x180003708  mov     rcx, [rax]
0x18000370b  mov     rax, [rcx+70h]
0x18000370f  mov     rcx, r8
0x180003712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003717  mov     r9, [rsp+120h+var_C0]; void (*)(void *)
0x18000371c  mov     r8, [rsp+120h+var_B8]
0x180003721  mov     eax, edi
0x180003723  mov     [rsp+120h+var_E0], eax
0x180003727  cmp     [r13+4], edi
0x18000372b  jbe     loc_180003AD8
0x180003731  mov     ebx, eax
0x180003733  mov     r10d, 100h
0x180003739  shl     rbx, 8
0x18000373d  add     rbx, [r13+8]
0x180003741  cmp     [rbx+40h], edi
0x180003744  jz      loc_1800038B8
0x18000374a  movzx   edx, word ptr [rsi]
0x18000374d  cmp     dx, 17h
0x180003751  jnz     short loc_18000378D
0x180003753  cmp     [rsi+8], di
0x180003757  jnz     short loc_180003788
0x180003759  cmp     [rsi+0Ah], di
0x18000375d  jnz     short loc_180003788
0x18000375f  cmp     [rsi+0Ch], di
0x180003763  jnz     short loc_180003788
0x180003765  cmp     [rsi+0Eh], di
0x180003769  jnz     short loc_180003788
0x18000376b  cmp     [rsi+10h], di
0x18000376f  jnz     short loc_180003788
0x180003771  cmp     [rsi+12h], di
0x180003775  jnz     short loc_180003788
0x180003777  cmp     [rsi+14h], di
0x18000377b  jnz     short loc_180003788
0x18000377d  cmp     [rsi+16h], r10w
0x180003782  jnz     short loc_180003788
0x180003784  mov     al, 1
0x180003786  jmp     short loc_180003794
0x180003788  mov     al, dil
0x18000378b  jmp     short loc_180003794
0x18000378d  cmp     byte ptr [rsi+4], 7Fh
0x180003791  setz    al
0x180003794  test    al, al
0x180003796  jz      short loc_1800037E8
0x180003798  cmp     word ptr [rbx+4], 17h
0x18000379d  jnz     short loc_1800037D9
0x18000379f  cmp     [rbx+0Ch], di
0x1800037a3  jnz     short loc_1800037D4
0x1800037a5  cmp     [rbx+0Eh], di
0x1800037a9  jnz     short loc_1800037D4
0x1800037ab  cmp     [rbx+10h], di
0x1800037af  jnz     short loc_1800037D4
0x1800037b1  cmp     [rbx+12h], di
0x1800037b5  jnz     short loc_1800037D4
0x1800037b7  cmp     [rbx+14h], di
0x1800037bb  jnz     short loc_1800037D4
0x1800037bd  cmp     [rbx+16h], di
0x1800037c1  jnz     short loc_1800037D4
0x1800037c3  cmp     [rbx+18h], di
0x1800037c7  jnz     short loc_1800037D4
0x1800037c9  cmp     [rbx+1Ah], r10w
0x1800037ce  jnz     short loc_1800037D4
0x1800037d0  mov     al, 1
0x1800037d2  jmp     short loc_1800037E0
0x1800037d4  mov     al, dil
0x1800037d7  jmp     short loc_1800037E0
0x1800037d9  cmp     byte ptr [rbx+8], 7Fh
0x1800037dd  setz    al
0x1800037e0  test    al, al
0x1800037e2  jnz     loc_180003989
0x1800037e8  movzx   ecx, word ptr [rbx+4]
0x1800037ec  cmp     cx, 17h
0x1800037f0  jnz     short loc_18000382B
0x1800037f2  cmp     [rbx+0Ch], di
0x1800037f6  jnz     short loc_180003826
0x1800037f8  cmp     [rbx+0Eh], di
0x1800037fc  jnz     short loc_180003826
0x1800037fe  cmp     [rbx+10h], di
0x180003802  jnz     short loc_180003826
0x180003804  cmp     [rbx+12h], di
0x180003808  jnz     short loc_180003826
0x18000380a  cmp     [rbx+14h], di
0x18000380e  jnz     short loc_180003826
0x180003810  cmp     [rbx+16h], di
0x180003814  jnz     short loc_180003826
0x180003816  cmp     [rbx+18h], di
0x18000381a  jnz     short loc_180003826
0x18000381c  cmp     [rbx+1Ah], di
0x180003820  jnz     short loc_180003826
0x180003822  mov     al, 1
0x180003824  jmp     short loc_180003831
0x180003826  mov     al, dil
0x180003829  jmp     short loc_180003831
0x18000382b  cmp     [rbx+8], edi
0x18000382e  setz    al
0x180003831  test    al, al
0x180003833  jz      short loc_18000383A
0x180003835  cmp     cx, dx
0x180003838  jmp     short loc_1800038B2
0x18000383a  cmp     dx, cx
0x18000383d  jnz     short loc_1800038B8
0x18000383f  cmp     [rbx+3Ch], edi
0x180003842  jnz     short loc_18000387F
0x180003844  cmp     dx, [rbx+20h]
0x180003848  jnz     short loc_1800038B8
0x18000384a  cmp     dx, 2
0x18000384e  jnz     short loc_18000385B
0x180003850  mov     eax, [rsi+4]
0x180003853  and     eax, [rbx+24h]
0x180003856  cmp     eax, [rbx+8]
0x180003859  jmp     short loc_1800038B2
0x18000385b  cmp     dx, 17h
0x18000385f  jnz     short loc_1800038B8
0x180003861  mov     edx, edi
0x180003863  mov     ecx, edx
0x180003865  movzx   eax, word ptr [rbx+rcx*2+28h]
0x18000386a  and     ax, [rsi+rcx*2+8]
0x18000386f  cmp     ax, [rbx+rcx*2+0Ch]
0x180003874  jnz     short loc_1800038B8
0x180003876  inc     edx
0x180003878  cmp     edx, 8
0x18000387b  jb      short loc_180003863
0x18000387d  jmp     short loc_1800038B2
0x18000387f  cmp     dx, 17h
0x180003883  jnz     short loc_1800038A6
0x180003885  cmp     cx, dx
0x180003888  jnz     short loc_1800038B8
0x18000388a  mov     eax, [rbx+1Ch]
0x18000388d  cmp     [rsi+18h], eax
0x180003890  jnz     short loc_1800038B8
0x180003892  mov     rax, [rbx+14h]
0x180003896  cmp     [rsi+10h], rax
0x18000389a  jnz     short loc_1800038B8
0x18000389c  mov     rax, [rbx+0Ch]
0x1800038a0  cmp     [rsi+8], rax
0x1800038a4  jmp     short loc_1800038B2
0x1800038a6  cmp     cx, 2
0x1800038aa  jnz     short loc_1800038B8
0x1800038ac  mov     eax, [rbx+8]
0x1800038af  cmp     [rsi+4], eax
0x1800038b2  jz      loc_180003989
0x1800038b8  cmp     [rbx+78h], edi
0x1800038bb  jz      loc_180003966
0x1800038c1  mov     rax, [rbx+68h]
0x1800038c5  movzx   edi, word ptr [rax]
0x1800038c8  cmp     di, 2Ah ; '*'
0x1800038cc  jnz     short loc_1800038D8
0x1800038ce  cmp     dword ptr [rbx+78h], 1
0x1800038d2  jz      loc_180003A31
0x1800038d8  mov     ecx, [r9+30h]; int
0x1800038dc  test    ecx, ecx
0x1800038de  jnz     short loc_180003923
0x1800038e0  mov     [rsp+120h+var_E8], r8; int *
0x1800038e5  lea     rax, [rsp+120h+var_DC]
0x1800038ea  mov     [rsp+120h+var_F0], rax; int *
0x1800038ef  lea     r8d, [rcx+1]; int
0x1800038f3  mov     rdx, rsi; struct sockaddr *
0x1800038f6  mov     [rsp+120h+var_F8], r9; struct STRU *
0x1800038fb  mov     [rsp+120h+var_DC], ecx
0x1800038ff  call    ?ReverseDNSLookup@IP_RESTRICTION_LIST@@SAJHPEAUsockaddr@@HP6AXPEAX@Z1PEAVSTRU@@PEAJPEAH@Z; IP_RESTRICTION_LIST::ReverseDNSLookup(int,sockaddr *,int,void (*)(void *),void *,STRU *,long *,int *)
0x180003904  test    eax, eax
0x180003906  js      loc_180003BE8
0x18000390c  mov     rax, [rsp+120h+var_B8]
0x180003911  cmp     dword ptr [rax], 0
0x180003914  jnz     loc_180003BE6
0x18000391a  mov     r9, [rsp+120h+var_C0]
0x18000391f  mov     ecx, [r9+30h]
0x180003923  mov     r8, [rbx+68h]
0x180003927  mov     eax, [rbx+78h]
0x18000392a  cmp     di, 2Ah ; '*'
0x18000392e  jnz     short loc_180003957
0x180003930  dec     eax
0x180003932  cmp     eax, ecx
0x180003934  ja      short loc_180003964
0x180003936  sub     rcx, rax
0x180003939  mov     rax, [r9+20h]
0x18000393d  lea     rdx, [rax+rcx*2]; String2
0x180003941  lea     rcx, [r8+2]; String1
0x180003945  call    cs:__imp__wcsicmp
0x18000394b  xor     edi, edi
0x18000394d  test    eax, eax
0x18000394f  jz      loc_180003A33
0x180003955  jmp     short loc_180003966
0x180003957  cmp     eax, ecx
0x180003959  jnz     short loc_180003964
0x18000395b  mov     rdx, [r9+20h]
0x18000395f  mov     rcx, r8
0x180003962  jmp     short loc_180003945
0x180003964  xor     edi, edi
0x180003966  mov     eax, [rsp+120h+var_E0]
0x18000396a  inc     eax
0x18000396c  mov     [rsp+120h+var_E0], eax
0x180003970  cmp     eax, [r13+4]
0x180003974  jnb     loc_180003AD8
0x18000397a  mov     r9, [rsp+120h+var_C0]
0x18000397f  mov     r8, [rsp+120h+var_B8]
0x180003984  jmp     loc_180003731
0x180003989  mov     eax, [rbx]
0x18000398b  mov     rcx, r15
0x18000398e  mov     [rcx], eax
0x180003990  cmp     dword ptr [r15], 1
0x180003994  jz      loc_180003BE6
0x18000399a  mov     rax, [r14]
0x18000399d  mov     rcx, r14
0x1800039a0  mov     rax, [rax+110h]
0x1800039a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039ac  mov     r8, rax
0x1800039af  lea     rdx, [rsp+120h+var_D8]
0x1800039b4  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800039bb  xorps   xmm0, xmm0
0x1800039be  mov     [rsp+120h+var_D8], rax
0x1800039c3  movdqu  [rsp+120h+var_D0], xmm0
0x1800039c9  mov     rcx, [r8]
0x1800039cc  mov     rax, [rcx]
0x1800039cf  mov     rcx, r8
0x1800039d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039d7  test    eax, eax
0x1800039d9  js      loc_180003BE6
0x1800039df  cmp     dword ptr [rsp+120h+var_D0+8], edi
0x1800039e3  jz      loc_180003BE6
0x1800039e9  cmp     dword ptr [rsp+120h+var_D0+4], 3
0x1800039ee  jb      loc_180003BE6
0x1800039f4  cmp     dword ptr [rsp+120h+var_D0], 4
0x1800039f9  jz      short loc_180003A06
0x1800039fb  test    byte ptr [rsp+120h+var_D0], 4
0x180003a00  jz      loc_180003BE6
0x180003a06  mov     ebx, 1
0x180003a0b  mov     word ptr [rsp+120h+var_DC], di
0x180003a10  mov     r8d, ebx
0x180003a13  lea     rdx, [rsp+120h+var_DC]
0x180003a18  lea     rcx, [rbp+37h+var_B0]
0x180003a1c  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003a22  lea     rdx, [rsp+120h+var_E0]
0x180003a27  mov     word ptr [rsp+120h+var_E0], di
0x180003a2c  jmp     loc_180003B90
0x180003a31  xor     edi, edi
0x180003a33  mov     eax, [rbx]
0x180003a35  mov     [r12], eax
0x180003a39  test    eax, eax
0x180003a3b  jnz     loc_180003BE6
0x180003a41  mov     rax, [r14]
0x180003a44  mov     rcx, r14
0x180003a47  mov     rax, [rax+110h]
0x180003a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a53  mov     r8, rax
0x180003a56  lea     rdx, [rsp+120h+var_D8]
0x180003a5b  lea     rax, ?ProviderGuid@?1??GetProviderGuid@WWWServerTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `WWWServerTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x180003a62  xorps   xmm0, xmm0
0x180003a65  mov     [rsp+120h+var_D8], rax
0x180003a6a  movdqu  [rsp+120h+var_D0], xmm0
0x180003a70  mov     rcx, [r8]
0x180003a73  mov     rax, [rcx]
0x180003a76  mov     rcx, r8
0x180003a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a7e  test    eax, eax
0x180003a80  js      loc_180003BE6
0x180003a86  cmp     dword ptr [rsp+120h+var_D0+8], edi
0x180003a8a  jz      loc_180003BE6
0x180003a90  cmp     dword ptr [rsp+120h+var_D0+4], 3
0x180003a95  jb      loc_180003BE6
0x180003a9b  cmp     dword ptr [rsp+120h+var_D0], 4
0x180003aa0  jz      short loc_180003AAD
0x180003aa2  test    byte ptr [rsp+120h+var_D0], 4
0x180003aa7  jz      loc_180003BE6
0x180003aad  mov     rax, [r14]
0x180003ab0  mov     rcx, r14
0x180003ab3  mov     rbx, [rsp+120h+var_C0]
0x180003ab8  mov     rax, [rax+110h]
0x180003abf  mov     rbx, [rbx+20h]
0x180003ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ac8  mov     r8, rbx; unsigned __int16 *
  ... truncated ...
```
