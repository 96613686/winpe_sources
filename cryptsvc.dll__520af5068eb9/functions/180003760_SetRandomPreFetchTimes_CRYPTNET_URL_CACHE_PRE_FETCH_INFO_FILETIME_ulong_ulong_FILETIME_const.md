# SetRandomPreFetchTimes(_CRYPTNET_URL_CACHE_PRE_FETCH_INFO *,_FILETIME *,ulong,ulong *,_FILETIME * const)

- ea: `0x180003760`
- end: `0x180003a3e`
- name: `?SetRandomPreFetchTimes@@YAXPEAU_CRYPTNET_URL_CACHE_PRE_FETCH_INFO@@PEAU_FILETIME@@KPEAKQEAU2@@Z`
- size: `734`
- prototype: `void __fastcall(struct _CRYPTNET_URL_CACHE_PRE_FETCH_INFO *, struct _FILETIME *, unsigned int, unsigned int *, struct _FILETIME *const lpFileTime2)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800033e0`

## callees

- `0x180003760`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003a14`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003a14`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003788`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800037f7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003895`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000391b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800039aa`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003788`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800037f7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180003895`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000391b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800039aa`
- `CRYPTBASE!SystemFunction036` at `0x1800037d1`
- `CRYPTBASE!SystemFunction036` at `0x1800037d1`

## pseudocode

```c
void __fastcall SetRandomPreFetchTimes(
        struct _CRYPTNET_URL_CACHE_PRE_FETCH_INFO *a1,
        struct _FILETIME *a2,
        unsigned int a3,
        unsigned int *a4,
        struct _FILETIME *const lpFileTime2)
{
  FILETIME *p_NextUpdateTime; // rsi
  __int64 v10; // rbp
  unsigned __int64 v11; // rdi
  DWORD TickCount; // eax
  unsigned __int64 v13; // r9
  int v14; // ecx
  unsigned int v15; // r10d
  unsigned int v16; // eax
  unsigned int v17; // r9d
  unsigned int v18; // r8d
  const FILETIME *v19; // rdx
  DWORD dwObjectType; // ecx
  unsigned int v21; // ebx
  unsigned int v22; // ecx
  int v23; // r8d
  DWORD v24; // edi
  FILETIME v25; // rax
  bool v26; // sf
  __int64 *p_RandomBuffer; // r8
  __int64 RandomBuffer; // [rsp+60h] [rbp+8h] BYREF
  FILETIME FileTime2; // [rsp+78h] [rbp+20h] BYREF

  p_NextUpdateTime = &a1->NextUpdateTime;
  v10 = 0;
  if ( CompareFileTime(&a1->NextUpdateTime, &a1->ThisUpdateTime) <= 0 )
    LODWORD(v11) = 0;
  else
    v11 = (*(_QWORD *)p_NextUpdateTime - *(_QWORD *)&a1->ThisUpdateTime) / 0x989680uLL;
  if ( a1->dwObjectType == 3 && (unsigned int)v11 < dword_180020284 )
    goto LABEL_27;
  LODWORD(RandomBuffer) = 0;
  if ( SystemFunction036(&RandomBuffer, 4u) )
    TickCount = RandomBuffer;
  else
    TickCount = GetTickCount();
  LODWORD(RandomBuffer) = TickCount;
  if ( a1->PublishTime.dwLowDateTime || a1->PublishTime.dwHighDateTime )
  {
    if ( CompareFileTime(p_NextUpdateTime, &a1->PublishTime) <= 0 )
      LODWORD(v13) = 0;
    else
      v13 = (*(_QWORD *)p_NextUpdateTime - *(_QWORD *)&a1->PublishTime) / 0x989680uLL;
    v14 = 0;
    v15 = (unsigned int)v13 / dword_180020288;
    v16 = (unsigned int)v13 / dword_18002028C;
    v17 = v13 - (unsigned int)v13 / dword_180020288;
    v18 = v17 - v16;
    if ( v17 <= v16 )
      v18 = 0;
    if ( v18 >= dword_180020290 && v18 )
    {
      if ( a3 )
      {
        v14 = a3 % (v18 >> 1);
        v18 -= v14;
      }
      v19 = lpFileTime2;
      *lpFileTime2 = (struct _FILETIME)(*(_QWORD *)&a1->PublishTime
                                      + 10000000LL * (v14 + v15 + (unsigned int)RandomBuffer % v18));
      if ( CompareFileTime(a2, v19) <= 0 )
        v10 = 1;
    }
  }
  dwObjectType = a1->dwObjectType;
  if ( dwObjectType - 6 > 1 )
  {
LABEL_43:
    if ( dwObjectType - 5 <= 1 )
    {
LABEL_21:
      v21 = dword_180020298;
      if ( (unsigned int)v11 / dword_180020294 < dword_180020298 )
      {
        v21 = (unsigned int)v11 / dword_180020294;
        if ( (unsigned int)v11 / dword_180020294 < dword_18002029C )
          v21 = dword_18002029C;
      }
      v22 = v21;
      if ( a3 )
      {
        v23 = a3 % (v21 >> 1);
        v22 = v21 - v23;
      }
      else
      {
        v23 = 0;
      }
      v24 = RandomBuffer;
      FileTime2 = (FILETIME)(*(_QWORD *)p_NextUpdateTime + 10000000LL * (v23 + (unsigned int)RandomBuffer % v22));
      if ( CompareFileTime(a2, &FileTime2) > 0 )
      {
        RandomBuffer = *(_QWORD *)p_NextUpdateTime + 10000000LL * v21;
        v26 = CompareFileTime(a2, (const FILETIME *)&RandomBuffer) < 0;
        p_RandomBuffer = &RandomBuffer;
        if ( !v26 )
          p_RandomBuffer = (__int64 *)a2;
        v25 = (FILETIME)(*p_RandomBuffer + 10000000LL * (v24 % dword_1800202A0));
      }
      else
      {
        v25 = FileTime2;
      }
      lpFileTime2[v10] = v25;
      LODWORD(v10) = v10 + 1;
    }
LABEL_27:
    *a4 = v10;
    return;
  }
  if ( (_DWORD)v10 || g_fLastHasNetworkCost )
  {
    if ( dwObjectType == 7 )
      goto LABEL_21;
    goto LABEL_43;
  }
  *lpFileTime2 = *a2;
  *a4 = 1;
}

```

## disassembly

```asm
0x180003760  push    rbx
0x180003762  push    rbp
0x180003763  push    rsi
0x180003764  push    rdi
0x180003765  push    r13
0x180003767  push    r14
0x180003769  push    r15
0x18000376b  sub     rsp, 20h
0x18000376f  mov     r13, rdx
0x180003772  lea     rsi, [rcx+18h]
0x180003776  lea     rdx, [rcx+10h]; lpFileTime2
0x18000377a  mov     rbx, rcx
0x18000377d  mov     rcx, rsi; lpFileTime1
0x180003780  mov     r14, r9
0x180003783  mov     r15d, r8d
0x180003786  xor     ebp, ebp
0x180003788  call    cs:__imp_CompareFileTime
0x18000378e  mov     rdx, 0D6BF94D5E57A42BDh
0x180003798  test    eax, eax
0x18000379a  jle     loc_180003A0D
0x1800037a0  mov     rcx, [rsi]
0x1800037a3  mov     rax, rdx
0x1800037a6  sub     rcx, [rbx+10h]
0x1800037aa  mul     rcx
0x1800037ad  mov     rdi, rdx
0x1800037b0  shr     rdi, 17h
0x1800037b4  cmp     dword ptr [rbx+4], 3
0x1800037b8  jz      loc_18000394A
0x1800037be  mov     edx, 4; RandomBufferLength
0x1800037c3  mov     [rsp+58h+arg_8], r12
0x1800037c8  lea     rcx, [rsp+58h+RandomBuffer]; RandomBuffer
0x1800037cd  mov     dword ptr [rsp+58h+RandomBuffer], ebp
0x1800037d1  call    cs:__imp_SystemFunction036
0x1800037d7  test    al, al
0x1800037d9  jz      loc_180003A14
0x1800037df  mov     eax, dword ptr [rsp+58h+RandomBuffer]
0x1800037e3  mov     dword ptr [rsp+58h+RandomBuffer], eax
0x1800037e7  cmp     [rbx+20h], ebp
0x1800037ea  jz      loc_180003968
0x1800037f0  lea     rdx, [rbx+20h]; lpFileTime2
0x1800037f4  mov     rcx, rsi; lpFileTime1
0x1800037f7  call    cs:__imp_CompareFileTime
0x1800037fd  test    eax, eax
0x1800037ff  jle     loc_180003A1F
0x180003805  mov     rcx, [rsi]
0x180003808  mov     rax, 0D6BF94D5E57A42BDh
0x180003812  sub     rcx, [rbx+20h]
0x180003816  mul     rcx
0x180003819  mov     r9, rdx
0x18000381c  shr     r9, 17h
0x180003820  xor     edx, edx
0x180003822  mov     eax, r9d
0x180003825  div     cs:dword_180020288
0x18000382b  xor     edx, edx
0x18000382d  xor     ecx, ecx
0x18000382f  mov     r10d, eax
0x180003832  mov     eax, r9d
0x180003835  div     cs:dword_18002028C
0x18000383b  sub     r9d, r10d
0x18000383e  mov     r8d, r9d
0x180003841  sub     r8d, eax
0x180003844  cmp     r9d, eax
0x180003847  cmovbe  r8d, ecx
0x18000384b  cmp     r8d, cs:dword_180020290
0x180003852  jb      loc_180003971
0x180003858  test    r8d, r8d
0x18000385b  jz      loc_180003971
0x180003861  test    r15d, r15d
0x180003864  jnz     loc_1800039D6
0x18000386a  mov     eax, dword ptr [rsp+58h+RandomBuffer]
0x18000386e  xor     edx, edx
0x180003870  div     r8d
0x180003873  lea     eax, [r10+rdx]
0x180003877  add     eax, ecx
0x180003879  imul    rcx, rax, 989680h
0x180003880  mov     rax, [rsp+58h+lpFileTime2]
0x180003888  add     rcx, [rbx+20h]
0x18000388c  mov     rdx, rax; lpFileTime2
0x18000388f  mov     [rax], rcx
0x180003892  mov     rcx, r13; lpFileTime1
0x180003895  call    cs:__imp_CompareFileTime
0x18000389b  test    eax, eax
0x18000389d  mov     r8d, 1
0x1800038a3  cmovle  ebp, r8d
0x1800038a7  mov     ecx, [rbx+4]
0x1800038aa  mov     r12, [rsp+58h+arg_8]
0x1800038af  lea     eax, [rcx-6]
0x1800038b2  cmp     eax, 1
0x1800038b5  ja      loc_180003A27
0x1800038bb  test    ebp, ebp
0x1800038bd  jnz     short loc_1800038CB
0x1800038bf  cmp     cs:?g_fLastHasNetworkCost@@3HA, ebp; int g_fLastHasNetworkCost
0x1800038c5  jz      loc_1800039EC
0x1800038cb  cmp     ecx, 7
0x1800038ce  jnz     loc_180003A27
0x1800038d4  mov     ebx, cs:dword_180020298
0x1800038da  xor     edx, edx
0x1800038dc  mov     eax, edi
0x1800038de  div     cs:dword_180020294
0x1800038e4  cmp     eax, ebx
0x1800038e6  jb      short loc_180003957
0x1800038e8  mov     ecx, ebx
0x1800038ea  test    r15d, r15d
0x1800038ed  jnz     loc_18000397C
0x1800038f3  xor     r8d, r8d
0x1800038f6  mov     edi, dword ptr [rsp+58h+RandomBuffer]
0x1800038fa  xor     edx, edx
0x1800038fc  mov     eax, edi
0x1800038fe  div     ecx
0x180003900  lea     eax, [r8+rdx]
0x180003904  imul    rcx, rax, 989680h
0x18000390b  lea     rdx, [rsp+58h+FileTime2]; lpFileTime2
0x180003910  add     rcx, [rsi]
0x180003913  mov     qword ptr [rsp+58h+FileTime2.dwLowDateTime], rcx
0x180003918  mov     rcx, r13; lpFileTime1
0x18000391b  call    cs:__imp_CompareFileTime
0x180003921  test    eax, eax
0x180003923  jg      short loc_180003991
0x180003925  mov     rax, qword ptr [rsp+58h+FileTime2.dwLowDateTime]
0x18000392a  mov     rdx, [rsp+58h+lpFileTime2]
0x180003932  mov     [rdx+rbp*8], rax
0x180003936  inc     ebp
0x180003938  mov     [r14], ebp
0x18000393b  add     rsp, 20h
0x18000393f  pop     r15
0x180003941  pop     r14
0x180003943  pop     r13
0x180003945  pop     rdi
0x180003946  pop     rsi
0x180003947  pop     rbp
0x180003948  pop     rbx
0x180003949  retn
0x18000394a  cmp     edi, cs:dword_180020284
0x180003950  jb      short loc_180003938
0x180003952  jmp     loc_1800037BE
0x180003957  cmp     eax, cs:dword_18002029C
0x18000395d  mov     ebx, eax
0x18000395f  cmovb   ebx, cs:dword_18002029C
0x180003966  jmp     short loc_1800038E8
0x180003968  cmp     [rbx+24h], ebp
0x18000396b  jnz     loc_1800037F0
0x180003971  mov     r8d, 1
0x180003977  jmp     loc_1800038A7
0x18000397c  shr     ecx, 1
0x18000397e  xor     edx, edx
0x180003980  mov     eax, r15d
0x180003983  div     ecx
0x180003985  mov     ecx, ebx
0x180003987  mov     r8d, edx
0x18000398a  sub     ecx, edx
0x18000398c  jmp     loc_1800038F6
0x180003991  mov     ecx, ebx
0x180003993  imul    rdx, rcx, 989680h
0x18000399a  mov     rcx, r13; lpFileTime1
0x18000399d  add     rdx, [rsi]
0x1800039a0  mov     [rsp+58h+RandomBuffer], rdx
0x1800039a5  lea     rdx, [rsp+58h+RandomBuffer]; lpFileTime2
0x1800039aa  call    cs:__imp_CompareFileTime
0x1800039b0  test    eax, eax
0x1800039b2  lea     r8, [rsp+58h+RandomBuffer]
0x1800039b7  mov     eax, edi
0x1800039b9  cmovns  r8, r13
0x1800039bd  xor     edx, edx
0x1800039bf  div     cs:dword_1800202A0
0x1800039c5  mov     ecx, edx
0x1800039c7  imul    rax, rcx, 989680h
0x1800039ce  add     rax, [r8]
0x1800039d1  jmp     loc_18000392A
0x1800039d6  mov     ecx, r8d
0x1800039d9  xor     edx, edx
0x1800039db  shr     ecx, 1
0x1800039dd  mov     eax, r15d
0x1800039e0  div     ecx
0x1800039e2  mov     ecx, edx
0x1800039e4  sub     r8d, edx
0x1800039e7  jmp     loc_18000386A
0x1800039ec  mov     rax, [r13+0]
0x1800039f0  mov     rdx, [rsp+58h+lpFileTime2]
0x1800039f8  mov     [rdx], rax
0x1800039fb  mov     [r14], r8d
0x1800039fe  add     rsp, 20h
0x180003a02  pop     r15
0x180003a04  pop     r14
0x180003a06  pop     r13
0x180003a08  pop     rdi
0x180003a09  pop     rsi
0x180003a0a  pop     rbp
0x180003a0b  pop     rbx
0x180003a0c  retn
0x180003a0d  xor     edi, edi
0x180003a0f  jmp     loc_1800037B4
0x180003a14  call    cs:__imp_GetTickCount
0x180003a1a  jmp     loc_1800037E3
0x180003a1f  xor     r9d, r9d
0x180003a22  jmp     loc_180003820
0x180003a27  sub     ecx, 5
0x180003a2a  jz      loc_1800038D4
0x180003a30  cmp     ecx, 1
0x180003a33  jnz     loc_180003938
0x180003a39  jmp     loc_1800038D4
```
