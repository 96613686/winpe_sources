# CNetDiagClient::LoadResultData(void)

- ea: `0x18000e2d4`
- end: `0x18000e5c0`
- name: `?LoadResultData@CNetDiagClient@@QEAAJXZ`
- size: `748`
- prototype: `__int64 __fastcall(CNetDiagClient *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x18000c440`
- `0x18000d22c`
- `0x18000d390`

## callees

- `0x180008b08`
- `0x18000c6b4`
- `0x18000c7e4`
- `0x18000c8fc`
- `0x18000c9b0`
- `0x18000cfa0`
- `0x18000e2d4`
- `0x18000f590`
- `0x18001f652`
- `0x18001f690`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000e34f`
- `ole32!CoTaskMemFree` at `0x18000e4df`
- `ole32!CoTaskMemFree` at `0x18000e4ed`
- `ole32!CoTaskMemFree` at `0x18000e571`
- `ole32!CoTaskMemFree` at `0x18000e34f`
- `ole32!CoTaskMemFree` at `0x18000e4df`
- `ole32!CoTaskMemFree` at `0x18000e4ed`
- `ole32!CoTaskMemFree` at `0x18000e571`
- `wdi!WdiGetParameterCount` at `0x18000e322`
- `wdi!WdiGetParameterCount` at `0x18000e322`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::LoadResultData(CNetDiagClient *this)
{
  __int64 v2; // rcx
  int v3; // r15d
  CNetDiagClient *v4; // rcx
  unsigned int v5; // r14d
  __int64 result; // rax
  unsigned int ParamType; // eax
  struct _GUID *v8; // r8
  int String; // eax
  LPVOID *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rdi
  CNetDiagClient *v15; // rcx
  void *v16; // rdx
  CNetDiagClient *v17; // rcx
  unsigned int v18; // [rsp+20h] [rbp-30h] BYREF
  void *v19; // [rsp+28h] [rbp-28h] BYREF
  unsigned int v20; // [rsp+30h] [rbp-20h] BYREF
  int v21; // [rsp+34h] [rbp-1Ch] BYREF
  struct _GUID v22; // [rsp+38h] [rbp-18h] BYREF

  v20 = 0;
  v2 = *((_QWORD *)this + 16);
  v19 = 0;
  v3 = 0;
  v22 = 0;
  v21 = 0;
  LODWORD(v4) = WdiGetParameterCount(v2, &v20);
  if ( (int)v4 < 0 )
    return (unsigned int)v4;
  v5 = *((_DWORD *)this + 34);
  if ( v20 < v5 )
  {
    LODWORD(v4) = -2147467259;
    return (unsigned int)v4;
  }
  if ( v20 == v5 )
  {
    CoTaskMemFree(*((LPVOID *)this + 6));
    result = 1;
    *((_QWORD *)this + 6) = 0;
    return result;
  }
  if ( v20 > v5 )
  {
    while ( 1 )
    {
      v18 = 0;
      ParamType = CNetDiagClient::GetParamType(this, v5, (enum CNetDiagClient::NdfParamType *)&v18, &v19);
      v4 = (CNetDiagClient *)ParamType;
      if ( (ParamType & 0x80000000) != 0 )
        return (unsigned int)v4;
      if ( v18 == 1 )
        break;
      switch ( v18 )
      {
        case 2u:
          v13 = *((unsigned int *)this + 492);
          if ( (unsigned int)v13 < 0xC )
          {
            v14 = 152 * v13;
            CoTaskMemFree(*((LPVOID *)this + 19 * v13 + 35));
            CoTaskMemFree(*(LPVOID *)((char *)this + v14 + 152));
            FreeRepairInfos((struct tagRepairInfo *)((char *)this + v14 + 168), 1u, 0);
            *(_QWORD *)((char *)this + v14 + 280) = 0;
            *(_QWORD *)((char *)this + v14 + 152) = 0;
            *(_DWORD *)((char *)this + v14 + 160) = 0;
            *(_DWORD *)((char *)this + v14 + 288) = 0;
            memset_0((char *)this + v14 + 168, 0, 0x70u);
            LODWORD(v4) = CNetDiagClient::ExtractRepairOption(
                            v15,
                            v19,
                            (CNetDiagClient *)((char *)this + 152 * *((unsigned int *)this + 492) + 144));
            if ( (int)v4 < 0 )
              return (unsigned int)v4;
            ++*((_DWORD *)this + 492);
          }
          break;
        case 3u:
          v11 = *((unsigned int *)this + 758);
          if ( (unsigned int)v11 < 0xC )
          {
            LODWORD(v4) = CNetDiagClient::ExtractRootCauseInfo(
                            v4,
                            v19,
                            (CNetDiagClient *)((char *)this + 88 * v11 + 1976));
            if ( (int)v4 < 0 )
              return (unsigned int)v4;
            v12 = 88LL * *((unsigned int *)this + 758);
            if ( *(_WORD *)((char *)this + v12 + 2056) )
            {
              if ( *(int *)(*(_QWORD *)((char *)this + v12 + 2048) + 40LL) < 0 )
                *(_DWORD *)((char *)this + v12 + 2024) |= 0x40000000u;
            }
            ++*((_DWORD *)this + 758);
          }
          break;
        case 4u:
          v10 = (LPVOID *)((char *)this + 56);
LABEL_35:
          CoTaskMemFree(*v10);
          v16 = v19;
          *v10 = 0;
          String = CNetDiagClient::ExtractString(v17, v16, (unsigned __int16 **)v10);
LABEL_36:
          LODWORD(v4) = String;
          if ( String < 0 )
            return (unsigned int)v4;
          break;
        case 8u:
          v8 = &v22;
          goto LABEL_19;
        case 9u:
          v18 = 0;
          LODWORD(v4) = CNetDiagClient::ExtractSimpleDataType((CNetDiagClient *)ParamType, v19, &v18, 4u);
          if ( (int)v4 < 0 )
            return (unsigned int)v4;
          if ( !v3 )
          {
            String = CNetDiagClient::StoreRepairExecution(this, &v22, v18);
            goto LABEL_36;
          }
          break;
        case 0xAu:
          v8 = (struct _GUID *)((char *)this + 3064);
LABEL_19:
          String = CNetDiagClient::ExtractSimpleDataType((CNetDiagClient *)ParamType, v19, v8, 0x10u);
          goto LABEL_36;
        case 0xBu:
          LODWORD(v4) = CNetDiagClient::ExtractSimpleDataType((CNetDiagClient *)ParamType, v19, &v21, 4u);
          if ( (int)v4 < 0 )
            return (unsigned int)v4;
          v3 = v21;
          break;
      }
      if ( ++v5 >= v20 )
        return (unsigned int)v4;
    }
    v10 = (LPVOID *)((char *)this + 48);
    goto LABEL_35;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e2d4  mov     [rsp-28h+arg_8], rbx
0x18000e2d9  mov     [rsp-28h+arg_10], rsi
0x18000e2de  push    rbp
0x18000e2df  push    rdi
0x18000e2e0  push    r12
0x18000e2e2  push    r14
0x18000e2e4  push    r15
0x18000e2e6  mov     rbp, rsp
0x18000e2e9  sub     rsp, 50h
0x18000e2ed  mov     rax, cs:__security_cookie
0x18000e2f4  xor     rax, rsp
0x18000e2f7  mov     [rbp+var_8], rax
0x18000e2fb  xor     r12d, r12d
0x18000e2fe  lea     rdx, [rbp+var_20]
0x18000e302  mov     rsi, rcx
0x18000e305  mov     [rbp+var_20], r12d
0x18000e309  mov     rcx, [rcx+80h]
0x18000e310  xorps   xmm0, xmm0
0x18000e313  mov     [rbp+var_28], r12
0x18000e317  mov     r15d, r12d
0x18000e31a  movups  xmmword ptr [rbp+var_18.Data1], xmm0
0x18000e31e  mov     [rbp+var_1C], r12d
0x18000e322  call    cs:__imp_WdiGetParameterCount
0x18000e328  mov     ecx, eax
0x18000e32a  test    eax, eax
0x18000e32c  js      loc_18000E599
0x18000e332  mov     r14d, [rsi+88h]
0x18000e339  cmp     [rbp+var_20], r14d
0x18000e33d  jnb     short loc_18000E349
0x18000e33f  mov     ecx, 80004005h
0x18000e344  jmp     loc_18000E599
0x18000e349  jnz     short loc_18000E363
0x18000e34b  mov     rcx, [rsi+30h]; pv
0x18000e34f  call    cs:__imp_CoTaskMemFree
0x18000e355  mov     eax, 1
0x18000e35a  mov     [rsi+30h], r12
0x18000e35e  jmp     loc_18000E59B
0x18000e363  jbe     loc_18000E599
0x18000e369  lea     r9, [rbp+var_28]; void **
0x18000e36d  mov     [rbp+var_30], r12d
0x18000e371  lea     r8, [rbp+var_30]; enum CNetDiagClient::NdfParamType *
0x18000e375  mov     edx, r14d; unsigned int
0x18000e378  mov     rcx, rsi; this
0x18000e37b  call    ?GetParamType@CNetDiagClient@@IEAAJIPEAW4NdfParamType@1@PEAPEAX@Z; CNetDiagClient::GetParamType(uint,CNetDiagClient::NdfParamType *,void * *)
0x18000e380  mov     ecx, eax; this
0x18000e382  test    eax, eax
0x18000e384  js      loc_18000E599
0x18000e38a  mov     edx, [rbp+var_30]
0x18000e38d  sub     edx, 1
0x18000e390  jz      loc_18000E56A
0x18000e396  sub     edx, 1
0x18000e399  jz      loc_18000E4C1
0x18000e39f  sub     edx, 1
0x18000e3a2  jz      loc_18000E45A
0x18000e3a8  sub     edx, 1
0x18000e3ab  jz      loc_18000E451
0x18000e3b1  sub     edx, 4
0x18000e3b4  jz      loc_18000E44B
0x18000e3ba  sub     edx, 1
0x18000e3bd  jz      short loc_18000E40C
0x18000e3bf  sub     edx, 1
0x18000e3c2  jz      short loc_18000E3F1
0x18000e3c4  cmp     edx, 1
0x18000e3c7  jnz     loc_18000E58C
0x18000e3cd  lea     r9d, [rdx+3]; unsigned int
0x18000e3d1  mov     rdx, [rbp+var_28]; void *
0x18000e3d5  lea     r8, [rbp+var_1C]; void *
0x18000e3d9  call    ?ExtractSimpleDataType@CNetDiagClient@@IEAAJPEAX0K@Z; CNetDiagClient::ExtractSimpleDataType(void *,void *,ulong)
0x18000e3de  mov     ecx, eax
0x18000e3e0  test    eax, eax
0x18000e3e2  js      loc_18000E599
0x18000e3e8  mov     r15d, [rbp+var_1C]
0x18000e3ec  jmp     loc_18000E58C
0x18000e3f1  lea     r8, [rsi+0BF8h]; void *
0x18000e3f8  mov     rdx, [rbp+var_28]; void *
0x18000e3fc  mov     r9d, 10h; unsigned int
0x18000e402  call    ?ExtractSimpleDataType@CNetDiagClient@@IEAAJPEAX0K@Z; CNetDiagClient::ExtractSimpleDataType(void *,void *,ulong)
0x18000e407  jmp     loc_18000E586
0x18000e40c  mov     rdx, [rbp+var_28]; void *
0x18000e410  lea     r8, [rbp+var_30]; void *
0x18000e414  mov     r9d, 4; unsigned int
0x18000e41a  mov     [rbp+var_30], r12d
0x18000e41e  call    ?ExtractSimpleDataType@CNetDiagClient@@IEAAJPEAX0K@Z; CNetDiagClient::ExtractSimpleDataType(void *,void *,ulong)
0x18000e423  mov     ecx, eax
0x18000e425  test    eax, eax
0x18000e427  js      loc_18000E599
0x18000e42d  test    r15d, r15d
0x18000e430  jnz     loc_18000E58C
0x18000e436  mov     r8d, [rbp+var_30]; unsigned int
0x18000e43a  lea     rdx, [rbp+var_18]; struct _GUID *
0x18000e43e  mov     rcx, rsi; this
0x18000e441  call    ?StoreRepairExecution@CNetDiagClient@@IEAAJAEAU_GUID@@I@Z; CNetDiagClient::StoreRepairExecution(_GUID &,uint)
0x18000e446  jmp     loc_18000E586
0x18000e44b  lea     r8, [rbp+var_18]
0x18000e44f  jmp     short loc_18000E3F8
0x18000e451  lea     rbx, [rsi+38h]
0x18000e455  jmp     loc_18000E56E
0x18000e45a  mov     eax, [rsi+0BD8h]
0x18000e460  cmp     eax, 0Ch
0x18000e463  jnb     loc_18000E58C
0x18000e469  mov     rdx, [rbp+var_28]; void *
0x18000e46d  imul    r8, rax, 58h ; 'X'
0x18000e471  add     r8, 7B8h
0x18000e478  add     r8, rsi; struct CRootCauseInfo *
0x18000e47b  call    ?ExtractRootCauseInfo@CNetDiagClient@@IEAAJPEAXPEAVCRootCauseInfo@@@Z; CNetDiagClient::ExtractRootCauseInfo(void *,CRootCauseInfo *)
0x18000e480  mov     ecx, eax
0x18000e482  test    eax, eax
0x18000e484  js      loc_18000E599
0x18000e48a  mov     eax, [rsi+0BD8h]
0x18000e490  imul    rdx, rax, 58h ; 'X'
0x18000e494  cmp     [rdx+rsi+808h], r12w
0x18000e49d  jbe     short loc_18000E4B6
0x18000e49f  mov     rax, [rdx+rsi+800h]
0x18000e4a7  cmp     [rax+28h], r12d
0x18000e4ab  jge     short loc_18000E4B6
0x18000e4ad  bts     dword ptr [rdx+rsi+7E8h], 1Eh
0x18000e4b6  inc     dword ptr [rsi+0BD8h]
0x18000e4bc  jmp     loc_18000E58C
0x18000e4c1  mov     eax, [rsi+7B0h]
0x18000e4c7  cmp     eax, 0Ch
0x18000e4ca  jnb     loc_18000E58C
0x18000e4d0  imul    rdi, rax, 98h
0x18000e4d7  mov     rcx, [rdi+rsi+118h]; pv
0x18000e4df  call    cs:__imp_CoTaskMemFree
0x18000e4e5  mov     rcx, [rdi+rsi+98h]; pv
0x18000e4ed  call    cs:__imp_CoTaskMemFree
0x18000e4f3  xor     r8d, r8d; int
0x18000e4f6  lea     rbx, [rdi+rsi]
0x18000e4fa  lea     rcx, [rbx+0A8h]; pv
0x18000e501  lea     edx, [r8+1]; unsigned int
0x18000e505  call    ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x18000e50a  xor     edx, edx; Val
0x18000e50c  mov     [rdi+rsi+118h], r12
0x18000e514  lea     rcx, [rbx+0A8h]; void *
0x18000e51b  mov     [rdi+rsi+98h], r12
0x18000e523  mov     [rdi+rsi+0A0h], r12d
0x18000e52b  mov     [rdi+rsi+120h], r12d
0x18000e533  lea     r8d, [rdx+70h]; Size
0x18000e537  call    memset_0
0x18000e53c  mov     eax, [rsi+7B0h]
0x18000e542  mov     rdx, [rbp+var_28]; void *
0x18000e546  imul    r8, rax, 98h
0x18000e54d  add     r8, 90h
0x18000e554  add     r8, rsi; struct CRepairInfo *
0x18000e557  call    ?ExtractRepairOption@CNetDiagClient@@IEAAJPEAXPEAVCRepairInfo@@@Z; CNetDiagClient::ExtractRepairOption(void *,CRepairInfo *)
0x18000e55c  mov     ecx, eax
0x18000e55e  test    eax, eax
0x18000e560  js      short loc_18000E599
0x18000e562  inc     dword ptr [rsi+7B0h]
0x18000e568  jmp     short loc_18000E58C
0x18000e56a  lea     rbx, [rsi+30h]
0x18000e56e  mov     rcx, [rbx]; pv
0x18000e571  call    cs:__imp_CoTaskMemFree
0x18000e577  mov     rdx, [rbp+var_28]; void *
0x18000e57b  mov     r8, rbx; unsigned __int16 **
0x18000e57e  mov     [rbx], r12
0x18000e581  call    ?ExtractString@CNetDiagClient@@IEAAJPEAXPEAPEAG@Z; CNetDiagClient::ExtractString(void *,ushort * *)
0x18000e586  mov     ecx, eax
0x18000e588  test    eax, eax
0x18000e58a  js      short loc_18000E599
0x18000e58c  inc     r14d
0x18000e58f  cmp     r14d, [rbp+var_20]
0x18000e593  jb      loc_18000E369
0x18000e599  mov     eax, ecx
0x18000e59b  mov     rcx, [rbp+var_8]
0x18000e59f  xor     rcx, rsp; StackCookie
0x18000e5a2  call    __security_check_cookie
0x18000e5a7  lea     r11, [rsp+50h+var_s0]
0x18000e5ac  mov     rbx, [r11+38h]
0x18000e5b0  mov     rsi, [r11+40h]
0x18000e5b4  mov     rsp, r11
0x18000e5b7  pop     r15
0x18000e5b9  pop     r14
0x18000e5bb  pop     r12
0x18000e5bd  pop     rdi
0x18000e5be  pop     rbp
0x18000e5bf  retn
```
