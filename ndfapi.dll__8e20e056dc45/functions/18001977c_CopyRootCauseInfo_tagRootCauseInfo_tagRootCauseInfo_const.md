# CopyRootCauseInfo(tagRootCauseInfo *,tagRootCauseInfo const *)

- ea: `0x18001977c`
- end: `0x18001995b`
- name: `?CopyRootCauseInfo@@YAJPEAUtagRootCauseInfo@@PEBU1@@Z`
- size: `479`
- prototype: `__int64 __fastcall(struct tagRootCauseInfo *, const struct tagRootCauseInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x180019af8`

## callees

- `0x180008b08`
- `0x180008c08`
- `0x180019590`
- `0x18001977c`
- `0x18001ad20`
- `0x18001f690`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18001982c`
- `ole32!CoTaskMemAlloc` at `0x18001982c`
- `ole32!CoTaskMemFree` at `0x1800198f0`
- `ole32!CoTaskMemFree` at `0x1800198f0`

## pseudocode

```c
__int64 __fastcall CopyRootCauseInfo(struct tagRootCauseInfo *a1, const struct tagRootCauseInfo *a2)
{
  const unsigned __int16 *pwszDescription; // r8
  int v5; // edi
  __int128 v6; // xmm1
  RepairInfoEx *pRepairs; // rdx
  __int64 v8; // rcx
  unsigned int repairCount; // r14d
  RepairInfoEx *v10; // r15
  unsigned __int16 v11; // r12
  __int64 v12; // r8
  USHORT v13; // ax
  unsigned int i; // ebx
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  tagRootCauseInfo pv; // [rsp+20h] [rbp-50h] BYREF

  if ( a1 && a2 )
  {
    pwszDescription = a2->pwszDescription;
    v5 = 0;
    *(_OWORD *)pv.rootCauseID.Data4 = *(_OWORD *)a2->rootCauseID.Data4;
    v6 = *(_OWORD *)&a2->pRepairs;
    *(_QWORD *)&pv.rootCauseID.Data1 = *(_QWORD *)&a2->rootCauseID.Data1;
    *(_QWORD *)&pv.repairCount = *((_QWORD *)&v6 + 1);
    pv.pRepairs = 0;
    pv.repairCount = 0;
    pv.pwszDescription = 0;
    *(_OWORD *)&pv.networkInterfaceID.Data2 = *(_OWORD *)&a2->networkInterfaceID.Data2;
    if ( pwszDescription )
    {
      v5 = UtilStringCopyWithAlloc(&pv.pwszDescription, 0xFFFFu, pwszDescription);
      if ( v5 < 0 )
        goto LABEL_20;
    }
    if ( a2->pRepairs && a2->repairCount )
    {
      pv.pRepairs = (RepairInfoEx *)CoTaskMemAlloc(120LL * a2->repairCount);
      pRepairs = pv.pRepairs;
      if ( !pv.pRepairs )
      {
        v5 = -2147024882;
LABEL_20:
        FreeRootCauseInfos(&pv, 1u, 0);
        return (unsigned int)v5;
      }
      v8 = 120LL * a2->repairCount;
      if ( v8 )
      {
        do
        {
          LOBYTE(pRepairs->repair.guid.Data1) = 0;
          pRepairs = (RepairInfoEx *)((char *)pRepairs + 1);
          --v8;
        }
        while ( v8 );
        pRepairs = pv.pRepairs;
      }
      repairCount = a2->repairCount;
      v10 = pRepairs;
      v11 = 0;
      if ( (_WORD)repairCount )
      {
        while ( 1 )
        {
          v12 = v11;
          pRepairs[v12].repairRank = a2->pRepairs[v12].repairRank;
          v5 = CopyRepairInfo(
                 &pv.pRepairs[v12].repair,
                 &a2->pRepairs[v12].repair,
                 (const unsigned __int16 *)(v12 * 120));
          if ( v5 < 0 )
            break;
          v13 = a2->repairCount;
          if ( ++v11 >= v13 )
            goto LABEL_23;
          pRepairs = pv.pRepairs;
        }
        if ( v10 )
        {
          for ( i = 0; i < repairCount; ++i )
            FreeRepairInfos(&v10[i].repair, 1u, 0);
          CoTaskMemFree(v10);
        }
        goto LABEL_20;
      }
      v13 = 0;
LABEL_23:
      pv.repairCount = v13;
    }
    v16 = *(_OWORD *)pv.rootCauseID.Data4;
    *(_OWORD *)&a1->pwszDescription = *(_OWORD *)&pv.pwszDescription;
    v17 = *(_OWORD *)&pv.networkInterfaceID.Data2;
    *(_OWORD *)a1->rootCauseID.Data4 = v16;
    v18 = *(_OWORD *)&pv.pRepairs;
    *(_OWORD *)&a1->networkInterfaceID.Data2 = v17;
    *(_OWORD *)&a1->pRepairs = v18;
    return (unsigned int)v5;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001977c  mov     [rsp-38h+arg_10], rbx
0x180019781  push    rbp
0x180019782  push    rsi
0x180019783  push    rdi
0x180019784  push    r12
0x180019786  push    r13
0x180019788  push    r14
0x18001978a  push    r15
0x18001978c  mov     rbp, rsp
0x18001978f  sub     rsp, 70h
0x180019793  mov     rax, cs:__security_cookie
0x18001979a  xor     rax, rsp
0x18001979d  mov     [rbp+var_10], rax
0x1800197a1  xor     r13d, r13d
0x1800197a4  mov     rbx, rdx
0x1800197a7  mov     rsi, rcx
0x1800197aa  test    rcx, rcx
0x1800197ad  jz      loc_180019932
0x1800197b3  test    rdx, rdx
0x1800197b6  jz      loc_180019932
0x1800197bc  movups  xmm1, xmmword ptr [rdx+10h]
0x1800197c0  mov     r8, [rdx]; unsigned __int16 *
0x1800197c3  mov     edi, r13d
0x1800197c6  lea     r12d, [r13+1]
0x1800197ca  movaps  xmmword ptr [rbp+pv.rootCauseID.Data4], xmm1
0x1800197ce  movups  xmm0, xmmword ptr [rdx]
0x1800197d1  movups  xmm1, xmmword ptr [rdx+30h]
0x1800197d5  movaps  xmmword ptr [rbp+pv.pwszDescription], xmm0
0x1800197d9  movaps  xmmword ptr [rbp+pv.pRepairs], xmm1
0x1800197dd  mov     [rbp+pv.pRepairs], r13
0x1800197e1  mov     [rbp+pv.repairCount], r13w
0x1800197e6  mov     [rbp+pv.pwszDescription], r13
0x1800197ea  movups  xmm0, xmmword ptr [rdx+20h]
0x1800197ee  movaps  xmmword ptr [rbp+pv.networkInterfaceID.Data2], xmm0
0x1800197f2  test    r8, r8
0x1800197f5  jz      short loc_18001980F
0x1800197f7  mov     edx, 0FFFFh; unsigned int
0x1800197fc  lea     rcx, [rbp+pv]; unsigned __int16 **
0x180019800  call    ?UtilStringCopyWithAlloc@@YAJPEAPEAGIPEBG@Z; UtilStringCopyWithAlloc(ushort * *,uint,ushort const *)
0x180019805  mov     edi, eax
0x180019807  test    eax, eax
0x180019809  js      loc_1800198F6
0x18001980f  cmp     [rbx+30h], r13
0x180019813  jz      loc_180019911
0x180019819  cmp     [rbx+38h], r13w
0x18001981e  jz      loc_180019911
0x180019824  movzx   eax, word ptr [rbx+38h]
0x180019828  imul    rcx, rax, 78h ; 'x'; cb
0x18001982c  call    cs:__imp_CoTaskMemAlloc
0x180019832  mov     [rbp+pv.pRepairs], rax
0x180019836  mov     rdx, rax
0x180019839  test    rax, rax
0x18001983c  jnz     short loc_180019848
0x18001983e  mov     edi, 8007000Eh
0x180019843  jmp     loc_1800198F6
0x180019848  movzx   eax, word ptr [rbx+38h]
0x18001984c  imul    rcx, rax, 78h ; 'x'
0x180019850  test    rcx, rcx
0x180019853  jz      short loc_180019864
0x180019855  mov     [rdx], r13b
0x180019858  add     rdx, r12
0x18001985b  sub     rcx, r12
0x18001985e  jnz     short loc_180019855
0x180019860  mov     rdx, [rbp+pv.pRepairs]
0x180019864  movzx   r14d, word ptr [rbx+38h]
0x180019869  mov     r15, rdx
0x18001986c  mov     r12d, r13d
0x18001986f  cmp     r13w, r14w
0x180019873  jnb     loc_180019909
0x180019879  movzx   eax, r12w
0x18001987d  imul    r8, rax, 78h ; 'x'
0x180019881  mov     rax, [rbx+30h]
0x180019885  movzx   ecx, word ptr [rax+r8+70h]
0x18001988b  mov     [r8+rdx+70h], cx
0x180019891  mov     rdx, [rbx+30h]
0x180019895  mov     rcx, [rbp+pv.pRepairs]
0x180019899  add     rdx, r8; struct tagRepairInfo *
0x18001989c  add     rcx, r8; struct tagRepairInfo *
0x18001989f  call    ?CopyRepairInfo@@YAJPEAUtagRepairInfo@@PEBU1@@Z; CopyRepairInfo(tagRepairInfo *,tagRepairInfo const *)
0x1800198a4  mov     edi, eax
0x1800198a6  test    eax, eax
0x1800198a8  js      short loc_1800198BE
0x1800198aa  movzx   eax, word ptr [rbx+38h]
0x1800198ae  inc     r12w
0x1800198b2  cmp     r12w, ax
0x1800198b6  jnb     short loc_18001990D
0x1800198b8  mov     rdx, [rbp+pv.pRepairs]
0x1800198bc  jmp     short loc_180019879
0x1800198be  mov     r12d, 1
0x1800198c4  test    r15, r15
0x1800198c7  jz      short loc_1800198F6
0x1800198c9  test    r14d, r14d
0x1800198cc  jz      short loc_1800198F6
0x1800198ce  mov     ebx, r13d
0x1800198d1  mov     eax, ebx
0x1800198d3  xor     r8d, r8d; int
0x1800198d6  imul    rcx, rax, 78h ; 'x'
0x1800198da  mov     edx, r12d; unsigned int
0x1800198dd  add     rcx, r15; pv
0x1800198e0  call    ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x1800198e5  add     ebx, r12d
0x1800198e8  cmp     ebx, r14d
0x1800198eb  jb      short loc_1800198D1
0x1800198ed  mov     rcx, r15; pv
0x1800198f0  call    cs:__imp_CoTaskMemFree
0x1800198f6  xor     r8d, r8d; int
0x1800198f9  lea     rcx, [rbp+pv]; pv
0x1800198fd  mov     edx, r12d; unsigned int
0x180019900  call    ?FreeRootCauseInfos@@YAXPEAUtagRootCauseInfo@@KH@Z; FreeRootCauseInfos(tagRootCauseInfo *,ulong,int)
0x180019905  mov     eax, edi
0x180019907  jmp     short loc_180019937
0x180019909  movzx   eax, r14w
0x18001990d  mov     [rbp+pv.repairCount], ax
0x180019911  movaps  xmm0, xmmword ptr [rbp+pv.pwszDescription]
0x180019915  movaps  xmm1, xmmword ptr [rbp+pv.rootCauseID.Data4]
0x180019919  movups  xmmword ptr [rsi], xmm0
0x18001991c  movaps  xmm0, xmmword ptr [rbp+pv.networkInterfaceID.Data2]
0x180019920  movups  xmmword ptr [rsi+10h], xmm1
0x180019924  movaps  xmm1, xmmword ptr [rbp+pv.pRepairs]
0x180019928  movups  xmmword ptr [rsi+20h], xmm0
0x18001992c  movups  xmmword ptr [rsi+30h], xmm1
0x180019930  jmp     short loc_180019905
0x180019932  mov     eax, 80070057h
0x180019937  mov     rcx, [rbp+var_10]
0x18001993b  xor     rcx, rsp; StackCookie
0x18001993e  call    __security_check_cookie
0x180019943  mov     rbx, [rsp+70h+arg_10]
0x18001994b  add     rsp, 70h
0x18001994f  pop     r15
0x180019951  pop     r14
0x180019953  pop     r13
0x180019955  pop     r12
0x180019957  pop     rdi
0x180019958  pop     rsi
0x180019959  pop     rbp
0x18001995a  retn
```
