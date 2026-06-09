# PAC_InitEx2(_SAMPR_USER_ALL_INFORMATION *,_SAMPR_GET_GROUPS_BUFFER *,_SID_AND_ATTRIBUTES_LIST *,void *,_UNICODE_STRING *,_UNICODE_STRING *,ulong,ulong,ulong,_PAC_INFO_BUFFER * *,_LARGE_INTEGER *,_LARGE_INTEGER *,_LSA_LAST_INTER_LOGON_INFO *,_PACTYPE * *)

- ea: `0x180044434`
- end: `0x180044663`
- name: `?PAC_InitEx2@@YAJPEAU_SAMPR_USER_ALL_INFORMATION@@PEAU_SAMPR_GET_GROUPS_BUFFER@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAXPEAU_UNICODE_STRING@@4KKKPEAPEAU_PAC_INFO_BUFFER@@PEAT_LARGE_INTEGER@@6PEAU_LSA_LAST_INTER_LOGON_INFO@@PEAPEAU_PACTYPE@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(struct _SAMPR_USER_ALL_INFORMATION *, struct _SAMPR_GET_GROUPS_BUFFER *, struct _SID_AND_ATTRIBUTES_LIST *, void *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, size_t Size, unsigned int, unsigned int, struct _PAC_INFO_BUFFER **, union _LARGE_INTEGER *Src, union _LARGE_INTEGER *, struct _LSA_LAST_INTER_LOGON_INFO *, struct _PACTYPE **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180004830`
- `0x180038e7c`

## callees

- `0x1800057f0`
- `0x180018870`
- `0x180021a54`
- `0x180044434`
- `0x180044770`
- `0x180044f8c`

## pseudocode

```c
__int64 __fastcall PAC_InitEx2(
        struct _SAMPR_USER_ALL_INFORMATION *a1,
        struct _SAMPR_GET_GROUPS_BUFFER *a2,
        struct _SID_AND_ATTRIBUTES_LIST *a3,
        void *a4,
        struct _UNICODE_STRING *a5,
        struct _UNICODE_STRING *a6,
        size_t Size,
        unsigned int a8,
        unsigned int a9,
        struct _PAC_INFO_BUFFER **a10,
        union _LARGE_INTEGER *Src,
        union _LARGE_INTEGER *a12,
        struct _LSA_LAST_INTER_LOGON_INFO *a13,
        struct _PACTYPE **a14)
{
  int v14; // edi
  size_t v15; // r15
  int v16; // ebx
  struct _PAC_INFO_BUFFER **v17; // r14
  unsigned int v18; // edx
  unsigned int i; // r8d
  unsigned int v20; // ecx
  unsigned int v21; // edx
  unsigned __int64 v22; // rbp
  unsigned int *v23; // rax
  unsigned int *v24; // rsi
  unsigned int v25; // ebx
  union _LARGE_INTEGER *v26; // rdx
  void *v27; // rbx
  unsigned int v28; // r12d
  void *v29; // rbp
  __int64 v30; // r15
  unsigned int j; // edi
  __int64 v32; // rbx
  __int64 v33; // rax
  __int64 v34; // rax
  unsigned __int8 v36; // [rsp+30h] [rbp-78h]
  unsigned __int8 v37; // [rsp+38h] [rbp-70h]
  union _LARGE_INTEGER *v38; // [rsp+40h] [rbp-68h]
  union _LARGE_INTEGER *v39; // [rsp+48h] [rbp-60h]
  struct _LSA_LAST_INTER_LOGON_INFO *v40; // [rsp+50h] [rbp-58h]

  Src = 0;
  LODWORD(Size) = 0;
  *a14 = 0;
  v14 = PAC_MarshallValidationInfo(
          a1,
          a2,
          a3,
          a4,
          a5,
          a6,
          v36,
          v37,
          v38,
          v39,
          v40,
          (unsigned __int8 **)&Src,
          (unsigned int *)&Size);
  if ( v14 >= 0 )
  {
    v15 = (unsigned int)Size;
    v16 = 1;
    v17 = a10;
    v18 = (Size + 7) & 0xFFFFFFF8;
    if ( a10 )
    {
      for ( i = 0; i < a9; ++i )
      {
        if ( v18 + ((*((_DWORD *)a10[i] + 1) + 7) & 0xFFFFFFF8) < v18 )
          goto LABEL_19;
        ++v16;
        v18 += (*((_DWORD *)a10[i] + 1) + 7) & 0xFFFFFFF8;
      }
    }
    v20 = v18 + 24;
    if ( v18 + 24 < v18 || (v21 = v20 + 16 * v16 + 24, v21 < v20) )
    {
LABEL_19:
      v14 = -1073741675;
    }
    else if ( v21 < 0xFFFF )
    {
      v22 = (v21 + 7) & 0xFFFFFFF8;
      v23 = (unsigned int *)basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, v22);
      v24 = v23;
      if ( v23 )
      {
        a8 = 0;
        v25 = v16 + 1;
        memset_0(v23, 0, v22);
        v26 = Src;
        *v24 = v25;
        v24[1] = 0;
        v24[2] = 1;
        v24[3] = v15;
        v27 = (void *)(((unsigned __int64)&v24[4 * v25 + 3] + 3) & 0xFFFFFFFFFFFFFFF8uLL);
        *((_QWORD *)v24 + 2) = v27;
        memcpy_0(v27, v26, v15);
        v28 = 1;
        v29 = (void *)(((unsigned __int64)v27 + v24[3] + 7) & 0xFFFFFFFFFFFFFFF8uLL);
        if ( a9 )
        {
          v30 = 0;
          for ( j = 0; j < a9; ++j )
          {
            v32 = 2LL * v28;
            v24[2 * v32 + 2] = *(_DWORD *)v17[v30];
            v24[2 * v32 + 3] = *((_DWORD *)v17[v30] + 1);
            *(_QWORD *)&v24[2 * v32 + 4] = v29;
            memcpy_0(v29, *((const void **)v17[v30] + 1), *((unsigned int *)v17[v30] + 1));
            v33 = v24[4 * v28++ + 3];
            v29 = (void *)(((unsigned __int64)v29 + v33 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
            ++v30;
          }
          v14 = a8;
        }
        else
        {
          v14 = 0;
        }
        v34 = 2LL * v28;
        v24[2 * v34 + 2] = 6;
        v24[2 * v34 + 3] = 20;
        *(_QWORD *)&v24[2 * v34 + 4] = v29;
        *a14 = (struct _PACTYPE *)v24;
      }
      else
      {
        v14 = -1073741670;
      }
    }
    else
    {
      v14 = -1073741637;
    }
  }
  Pku2uFree(Src);
  Pku2uFree(0);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180044434  mov     r11, rsp
0x180044437  push    rbx
0x180044438  push    rbp
0x180044439  push    rsi
0x18004443a  push    rdi
0x18004443b  push    r12
0x18004443d  push    r14
0x18004443f  push    r15
0x180044441  sub     rsp, 70h
0x180044445  mov     rax, [rsp+0A8h+arg_68]
0x18004444d  xor     r12d, r12d
0x180044450  mov     [r11+58h], r12
0x180044454  mov     [r11+38h], r12d
0x180044458  mov     [rax], r12
0x18004445b  lea     rax, [r11+38h]
0x18004445f  mov     [r11-48h], rax
0x180044463  lea     rax, [r11+58h]
0x180044467  mov     [r11-50h], rax
0x18004446b  mov     rax, [rsp+0A8h+arg_28]
0x180044473  mov     [r11-80h], rax
0x180044477  mov     rax, [rsp+0A8h+arg_20]
0x18004447f  mov     [rsp+0A8h+var_88], rax; struct _UNICODE_STRING *
0x180044484  call    ?PAC_MarshallValidationInfo@@YAJPEAU_SAMPR_USER_ALL_INFORMATION@@PEAU_SAMPR_GET_GROUPS_BUFFER@@PEAU_SID_AND_ATTRIBUTES_LIST@@PEAXPEAU_UNICODE_STRING@@4EEPEAT_LARGE_INTEGER@@5PEAU_LSA_LAST_INTER_LOGON_INFO@@PEAPEAEPEAK@Z; PAC_MarshallValidationInfo(_SAMPR_USER_ALL_INFORMATION *,_SAMPR_GET_GROUPS_BUFFER *,_SID_AND_ATTRIBUTES_LIST *,void *,_UNICODE_STRING *,_UNICODE_STRING *,uchar,uchar,_LARGE_INTEGER *,_LARGE_INTEGER *,_LSA_LAST_INTER_LOGON_INFO *,uchar * *,ulong *)
0x180044489  mov     edi, eax
0x18004448b  test    eax, eax
0x18004448d  js      loc_18004463E
0x180044493  mov     r15d, dword ptr [rsp+0A8h+Size]
0x18004449b  lea     ebx, [r12+1]
0x1800444a0  mov     r14, [rsp+0A8h+arg_48]
0x1800444a8  mov     r9d, 0FFFFFFF8h
0x1800444ae  lea     edx, [r15+7]
0x1800444b2  and     edx, r9d
0x1800444b5  test    r14, r14
0x1800444b8  jz      short loc_1800444EA
0x1800444ba  mov     r8d, r12d
0x1800444bd  cmp     r8d, [rsp+0A8h+arg_40]
0x1800444c5  jnb     short loc_1800444EA
0x1800444c7  mov     eax, r8d
0x1800444ca  mov     rcx, [r14+rax*8]
0x1800444ce  mov     ecx, [rcx+4]
0x1800444d1  add     ecx, 7
0x1800444d4  and     ecx, r9d
0x1800444d7  add     ecx, edx
0x1800444d9  cmp     ecx, edx
0x1800444db  jb      loc_180044639
0x1800444e1  inc     ebx
0x1800444e3  mov     edx, ecx
0x1800444e5  inc     r8d
0x1800444e8  jmp     short loc_1800444BD
0x1800444ea  lea     ecx, [rdx+18h]
0x1800444ed  cmp     ecx, edx
0x1800444ef  jb      loc_180044639
0x1800444f5  mov     edx, ebx
0x1800444f7  shl     edx, 4
0x1800444fa  add     edx, 18h
0x1800444fd  add     edx, ecx
0x1800444ff  cmp     edx, ecx
0x180044501  jb      loc_180044639
0x180044507  cmp     edx, 0FFFFh
0x18004450d  jb      short loc_180044519
0x18004450f  mov     edi, 0C00000BBh
0x180044514  jmp     loc_18004463E
0x180044519  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x180044520  lea     ebp, [rdx+7]
0x180044523  and     rbp, r9
0x180044526  mov     rdx, rbp; unsigned __int64
0x180044529  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18004452e  mov     rsi, rax
0x180044531  test    rax, rax
0x180044534  jnz     short loc_180044540
0x180044536  mov     edi, 0C000009Ah
0x18004453b  jmp     loc_18004463E
0x180044540  mov     r8, rbp; Size
0x180044543  mov     [rsp+0A8h+arg_38], r12d
0x18004454b  xor     edx, edx; Val
0x18004454d  mov     rcx, rsi; void *
0x180044550  inc     ebx
0x180044552  call    memset_0
0x180044557  mov     rdx, [rsp+0A8h+Src]; Src
0x18004455f  mov     r8, r15; Size
0x180044562  mov     [rsi], ebx
0x180044564  mov     [rsi+4], r12d
0x180044568  shl     rbx, 4
0x18004456c  add     rbx, 0Fh
0x180044570  mov     dword ptr [rsi+8], 1
0x180044577  add     rbx, rsi
0x18004457a  mov     [rsi+0Ch], r15d
0x18004457e  and     rbx, 0FFFFFFFFFFFFFFF8h
0x180044582  mov     rcx, rbx; void *
0x180044585  mov     [rsi+10h], rbx
0x180044589  call    memcpy_0
0x18004458e  mov     ebp, [rsi+0Ch]
0x180044591  mov     r12d, 1
0x180044597  add     rbp, 7
0x18004459b  add     rbp, rbx
0x18004459e  and     rbp, 0FFFFFFFFFFFFFFF8h
0x1800445a2  cmp     [rsp+0A8h+arg_40], 0
0x1800445aa  jbe     short loc_18004460F
0x1800445ac  xor     r15d, r15d
0x1800445af  mov     edi, r15d
0x1800445b2  mov     rax, [r14+r15*8]
0x1800445b6  mov     ebx, r12d
0x1800445b9  add     rbx, rbx
0x1800445bc  mov     ecx, [rax]
0x1800445be  mov     [rsi+rbx*8+8], ecx
0x1800445c2  mov     rax, [r14+r15*8]
0x1800445c6  mov     ecx, [rax+4]
0x1800445c9  mov     [rsi+rbx*8+0Ch], ecx
0x1800445cd  mov     rcx, rbp; void *
0x1800445d0  mov     [rsi+rbx*8+10h], rbp
0x1800445d5  mov     rdx, [r14+r15*8]
0x1800445d9  mov     r8d, [rdx+4]; Size
0x1800445dd  mov     rdx, [rdx+8]; Src
0x1800445e1  call    memcpy_0
0x1800445e6  mov     eax, [rsi+rbx*8+0Ch]
0x1800445ea  add     rbp, 7
0x1800445ee  add     rbp, rax
0x1800445f1  inc     r12d
0x1800445f4  and     rbp, 0FFFFFFFFFFFFFFF8h
0x1800445f8  inc     edi
0x1800445fa  inc     r15
0x1800445fd  cmp     edi, [rsp+0A8h+arg_40]
0x180044604  jb      short loc_1800445B2
0x180044606  mov     edi, [rsp+0A8h+arg_38]
0x18004460d  jmp     short loc_180044611
0x18004460f  xor     edi, edi
0x180044611  mov     eax, r12d
0x180044614  add     rax, rax
0x180044617  mov     dword ptr [rsi+rax*8+8], 6
0x18004461f  mov     dword ptr [rsi+rax*8+0Ch], 14h
0x180044627  mov     [rsi+rax*8+10h], rbp
0x18004462c  mov     rax, [rsp+0A8h+arg_68]
0x180044634  mov     [rax], rsi
0x180044637  jmp     short loc_18004463E
0x180044639  mov     edi, 0C0000095h
0x18004463e  mov     rcx, [rsp+0A8h+Src]; void *
0x180044646  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18004464b  xor     ecx, ecx; void *
0x18004464d  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x180044652  mov     eax, edi
0x180044654  add     rsp, 70h
0x180044658  pop     r15
0x18004465a  pop     r14
0x18004465c  pop     r12
0x18004465e  pop     rdi
0x18004465f  pop     rsi
0x180044660  pop     rbp
0x180044661  pop     rbx
0x180044662  retn
```
