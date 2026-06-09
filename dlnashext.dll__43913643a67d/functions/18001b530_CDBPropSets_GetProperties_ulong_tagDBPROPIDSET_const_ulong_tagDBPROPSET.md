# CDBPropSets::GetProperties(ulong,tagDBPROPIDSET const *,ulong *,tagDBPROPSET * *)

- ea: `0x18001b530`
- end: `0x18001b791`
- name: `?GetProperties@CDBPropSets@@QEAAJKPEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z`
- size: `609`
- prototype: `int(CDBPropSets *__hidden this, unsigned int, const struct tagDBPROPIDSET *, unsigned int *, struct tagDBPROPSET **)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b440`
- `0x18001b450`
- `0x18001b460`

## callees

- `0x18000ab90`
- `0x18001af24`
- `0x18001b530`
- `0x18001b798`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b73e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b778`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b73e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b778`
- `OLEAUT32!__imp_VariantClear` at `0x18001b72a`
- `OLEAUT32!__imp_VariantClear` at `0x18001b72a`

## pseudocode

```c
__int64 __fastcall CDBPropSets::GetProperties(
        CDBPropSets *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5)
{
  unsigned int v5; // ebp
  int Property; // ebx
  struct tagDBPROPSET *v7; // rdi
  void *v8; // rcx
  const struct tagDBPROPIDSET *v9; // r9
  int v10; // eax
  unsigned int v11; // r15d
  int v12; // esi
  __int64 v13; // r13
  struct tagDBPROPSET *v14; // r14
  unsigned __int64 cPropertyIDs; // rcx
  void *v16; // rcx
  const struct tagDBPROPIDSET *v17; // r9
  int v18; // eax
  ULONG v19; // eax
  __int64 v20; // r12
  DBPROPID *rgPropertyIDs; // rax
  DBPROP *rgProperties; // rcx
  unsigned int v23; // r15d
  __int64 v24; // r13
  __int64 v25; // r14
  __int64 i; // rsi
  unsigned __int64 v28; // [rsp+20h] [rbp-68h] BYREF
  void *v29; // [rsp+28h] [rbp-60h] BYREF
  struct tagDBPROPSET *v30; // [rsp+30h] [rbp-58h]

  v5 = a2;
  Property = -2147024809;
  *a4 = 0;
  *a5 = 0;
  if ( a2 )
  {
    v7 = 0;
    v30 = 0;
    v29 = 0;
    v28 = 0;
    Property = ULongLongMult(a2, 0x20u, &v28);
    if ( Property >= 0 )
    {
      v10 = CTCoAllocPolicy::Alloc(v8, 1u, v28, &v29);
      v7 = (struct tagDBPROPSET *)v29;
      Property = v10;
      v9 = a3;
      v30 = (struct tagDBPROPSET *)v29;
    }
    if ( Property >= 0 )
    {
      v11 = 0;
      v12 = 0;
      LODWORD(v28) = 0;
      if ( v5 )
      {
        while ( Property >= 0 )
        {
          v13 = v11;
          v29 = 0;
          v14 = &v7[v13];
          v14->guidPropertySet = v9[v13].guidPropertySet;
          cPropertyIDs = v9[v13].cPropertyIDs;
          v14->rgProperties = 0;
          Property = ULongLongMult(cPropertyIDs, 0x48u, (unsigned __int64 *)&v29);
          if ( Property >= 0 )
          {
            v18 = CTCoAllocPolicy::Alloc(v16, 1u, (unsigned __int64)v29, (void **)&v7[v13].rgProperties);
            v17 = a3;
            Property = v18;
          }
          if ( Property >= 0 )
          {
            v19 = v17[v13].cPropertyIDs;
            v20 = 0;
            v14->cProperties = v19;
            if ( v19 )
            {
              do
              {
                if ( Property < 0 )
                  break;
                rgPropertyIDs = a3[v11].rgPropertyIDs;
                rgProperties = v14->rgProperties;
                v29 = (void *)(9 * v20);
                *(&rgProperties->dwPropertyID + 2 * (_QWORD)v29) = rgPropertyIDs[v20];
                Property = CDBPropSets::GetProperty(
                             this,
                             &v14->guidPropertySet,
                             v14->rgProperties[v20].dwPropertyID,
                             &v14->rgProperties[v20].vValue);
                if ( Property == -2147023728 )
                {
                  v12 = 1;
                  Property = 0;
                  *(&v14->rgProperties->dwStatus + 2 * (_QWORD)v29) = 1;
                }
                v20 = (unsigned int)(v20 + 1);
              }
              while ( (unsigned int)v20 < v14->cProperties );
              v7 = v30;
              v5 = a2;
              v11 = v28;
            }
          }
          v9 = a3;
          LODWORD(v28) = ++v11;
          if ( v11 >= v5 )
          {
            if ( Property >= 0 )
              goto LABEL_23;
            break;
          }
        }
        v23 = 0;
        v24 = 0;
        do
        {
          v25 = 0;
          for ( i = v24; (unsigned int)v25 < v7[i].cProperties; v25 = (unsigned int)(v25 + 1) )
            VariantClear((VARIANTARG *)((char *)&v7[i].rgProperties->vValue + 64 * v25 + 8 * v25));
          CoTaskMemFree(v7[i].rgProperties);
          ++v23;
          ++v24;
        }
        while ( v23 < v5 );
      }
      else
      {
LABEL_23:
        *a4 = v5;
        *a5 = v7;
        v7 = 0;
        if ( v12 )
          Property = 265946;
        else
          Property = 0;
      }
      CoTaskMemFree(v7);
    }
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18001b530  mov     r11, rsp
0x18001b533  mov     [r11+20h], r9
0x18001b537  mov     [r11+18h], r8
0x18001b53b  mov     [rsp+arg_8], edx
0x18001b53f  mov     [r11+8], rcx
0x18001b543  push    rbx
0x18001b544  push    rbp
0x18001b545  push    rsi
0x18001b546  push    rdi
0x18001b547  push    r12
0x18001b549  push    r13
0x18001b54b  push    r14
0x18001b54d  push    r15
0x18001b54f  sub     rsp, 48h
0x18001b553  mov     ebp, edx
0x18001b555  mov     rax, r9
0x18001b558  mov     r9, r8
0x18001b55b  mov     ebx, 80070057h
0x18001b560  mov     dword ptr [rax], 0
0x18001b566  mov     rax, [rsp+88h+arg_20]
0x18001b56e  mov     qword ptr [rax], 0
0x18001b575  test    edx, edx
0x18001b577  jz      loc_18001B77E
0x18001b57d  xor     edi, edi
0x18001b57f  lea     r8, [r11-68h]; unsigned __int64 *
0x18001b583  mov     ecx, ebp; unsigned __int64
0x18001b585  mov     [rsp+88h+var_58], rdi
0x18001b58a  mov     [r11-60h], rdi
0x18001b58e  mov     [r11-68h], rdi
0x18001b592  lea     edx, [rdi+20h]; unsigned __int64
0x18001b595  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001b59a  mov     ebx, eax
0x18001b59c  test    eax, eax
0x18001b59e  js      short loc_18001B5C6
0x18001b5a0  mov     r8, [rsp+88h+var_68]; unsigned __int64
0x18001b5a5  lea     r9, [rsp+88h+var_60]; void **
0x18001b5aa  lea     edx, [rdi+1]; unsigned int
0x18001b5ad  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18001b5b2  mov     rdi, [rsp+88h+var_60]
0x18001b5b7  mov     ebx, eax
0x18001b5b9  mov     r9, [rsp+88h+arg_10]
0x18001b5c1  mov     [rsp+88h+var_58], rdi
0x18001b5c6  test    ebx, ebx
0x18001b5c8  js      loc_18001B77E
0x18001b5ce  xor     r15d, r15d
0x18001b5d1  xor     esi, esi
0x18001b5d3  mov     dword ptr [rsp+88h+var_68], r15d
0x18001b5d8  test    ebp, ebp
0x18001b5da  jz      loc_18001B751
0x18001b5e0  test    ebx, ebx
0x18001b5e2  js      loc_18001B700
0x18001b5e8  mov     r13d, r15d
0x18001b5eb  lea     r8, [rsp+88h+var_60]; unsigned __int64 *
0x18001b5f0  shl     r13, 5
0x18001b5f4  mov     edx, 48h ; 'H'; unsigned __int64
0x18001b5f9  mov     [rsp+88h+var_60], 0
0x18001b602  movups  xmm0, xmmword ptr [r9+r13+0Ch]
0x18001b608  lea     r14, [rdi+r13]
0x18001b60c  movdqu  xmmword ptr [r14+0Ch], xmm0
0x18001b612  mov     ecx, [r9+r13+8]; unsigned __int64
0x18001b617  mov     qword ptr [r14], 0
0x18001b61e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001b623  mov     ebx, eax
0x18001b625  test    eax, eax
0x18001b627  js      short loc_18001B645
0x18001b629  mov     r8, [rsp+88h+var_60]; unsigned __int64
0x18001b62e  mov     r9, r14; void **
0x18001b631  mov     edx, 1; unsigned int
0x18001b636  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18001b63b  mov     r9, [rsp+88h+arg_10]
0x18001b643  mov     ebx, eax
0x18001b645  test    ebx, ebx
0x18001b647  js      loc_18001B6E3
0x18001b64d  mov     eax, [r9+r13+8]
0x18001b652  xor     r12d, r12d
0x18001b655  mov     [r14+8], eax
0x18001b659  test    eax, eax
0x18001b65b  jz      loc_18001B6E3
0x18001b661  mov     rbp, [rsp+88h+arg_10]
0x18001b669  mov     r15, [rsp+88h+arg_0]
0x18001b671  test    ebx, ebx
0x18001b673  js      short loc_18001B6D2
0x18001b675  mov     rax, [rbp+r13+0]
0x18001b67a  lea     r10, [r12+r12*8]
0x18001b67e  mov     rcx, [r14]
0x18001b681  lea     r9, [r10+6]
0x18001b685  lea     rdx, [r14+0Ch]; struct _GUID *
0x18001b689  mov     [rsp+88h+var_60], r10
0x18001b68e  mov     eax, [rax+r12*4]
0x18001b692  mov     [rcx+r10*8], eax
0x18001b696  mov     rcx, r15; this
0x18001b699  mov     r8, [r14]
0x18001b69c  lea     r9, [r8+r9*8]; struct tagVARIANT *
0x18001b6a0  mov     r8d, [r8+r10*8]; unsigned int
0x18001b6a4  call    ?GetProperty@CDBPropSets@@QEAAJAEBU_GUID@@KPEAUtagVARIANT@@@Z; CDBPropSets::GetProperty(_GUID const &,ulong,tagVARIANT *)
0x18001b6a9  mov     ebx, eax
0x18001b6ab  cmp     eax, 80070490h
0x18001b6b0  jnz     short loc_18001B6C9
0x18001b6b2  mov     rax, [r14]
0x18001b6b5  mov     esi, 1
0x18001b6ba  mov     rcx, [rsp+88h+var_60]
0x18001b6bf  xor     ebx, ebx
0x18001b6c1  mov     dword ptr [rax+rcx*8+8], 1
0x18001b6c9  inc     r12d
0x18001b6cc  cmp     r12d, [r14+8]
0x18001b6d0  jb      short loc_18001B671
0x18001b6d2  mov     rdi, [rsp+88h+var_58]
0x18001b6d7  mov     ebp, [rsp+88h+arg_8]
0x18001b6de  mov     r15d, dword ptr [rsp+88h+var_68]
0x18001b6e3  mov     r9, [rsp+88h+arg_10]
0x18001b6eb  inc     r15d
0x18001b6ee  mov     dword ptr [rsp+88h+var_68], r15d
0x18001b6f3  cmp     r15d, ebp
0x18001b6f6  jb      loc_18001B5E0
0x18001b6fc  test    ebx, ebx
0x18001b6fe  jns     short loc_18001B751
0x18001b700  xor     r15d, r15d
0x18001b703  xor     r13d, r13d
0x18001b706  mov     rsi, r13
0x18001b709  xor     r14d, r14d
0x18001b70c  shl     rsi, 5
0x18001b710  cmp     [rsi+rdi+8], r14d
0x18001b715  jbe     short loc_18001B73A
0x18001b717  mov     rax, [rsi+rdi]
0x18001b71b  lea     rcx, ds:6[r14*8]
0x18001b723  add     rcx, r14
0x18001b726  lea     rcx, [rax+rcx*8]; pvarg
0x18001b72a  call    cs:__imp_VariantClear
0x18001b730  inc     r14d
0x18001b733  cmp     r14d, [rsi+rdi+8]
0x18001b738  jb      short loc_18001B717
0x18001b73a  mov     rcx, [rsi+rdi]; pv
0x18001b73e  call    cs:__imp_CoTaskMemFree
0x18001b744  inc     r15d
0x18001b747  inc     r13
0x18001b74a  cmp     r15d, ebp
0x18001b74d  jb      short loc_18001B706
0x18001b74f  jmp     short loc_18001B775
0x18001b751  mov     rax, [rsp+88h+arg_18]
0x18001b759  mov     [rax], ebp
0x18001b75b  mov     rax, [rsp+88h+arg_20]
0x18001b763  mov     [rax], rdi
0x18001b766  xor     edi, edi
0x18001b768  test    esi, esi
0x18001b76a  jz      short loc_18001B773
0x18001b76c  mov     ebx, 40EDAh
0x18001b771  jmp     short loc_18001B775
0x18001b773  xor     ebx, ebx
0x18001b775  mov     rcx, rdi; pv
0x18001b778  call    cs:__imp_CoTaskMemFree
0x18001b77e  mov     eax, ebx
0x18001b780  add     rsp, 48h
0x18001b784  pop     r15
0x18001b786  pop     r14
0x18001b788  pop     r13
0x18001b78a  pop     r12
0x18001b78c  pop     rdi
0x18001b78d  pop     rsi
0x18001b78e  pop     rbp
0x18001b78f  pop     rbx
0x18001b790  retn
```
