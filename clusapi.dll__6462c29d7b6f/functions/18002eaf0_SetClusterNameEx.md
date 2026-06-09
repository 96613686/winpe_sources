# SetClusterNameEx

- ea: `0x18002eaf0`
- end: `0x18002ecd3`
- name: `SetClusterNameEx`
- size: `483`
- prototype: `__int64 __fastcall(struct _HCLUSTER *, wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002eae0`

## callees

- `0x18001236c`
- `0x180014638`
- `0x180016b6c`
- `0x180016d58`
- `0x18001d1e8`
- `0x18001e58c`
- `0x18001e5f0`
- `0x18002139c`
- `0x180026ef4`
- `0x18002eaf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ecad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ecad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ec8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ec8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ec98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ec98`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ebb1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002ebb1`
- `api-ms-win-security-base-l1-1-0!AreAnyAccessesGranted` at `0x18002eb47`
- `api-ms-win-security-base-l1-1-0!AreAnyAccessesGranted` at `0x18002eb47`

## pseudocode

```c
__int64 __fastcall SetClusterNameEx(struct _HCLUSTER *a1, wchar_t *a2, wchar_t *a3)
{
  __int64 v6; // rcx
  __int64 result; // rax
  UINT v8; // r11d
  unsigned int v9; // r8d
  unsigned __int64 v10; // rdi
  wchar_t *v11; // rax
  wchar_t *v12; // rbx
  unsigned int v13; // r14d
  int v14; // eax
  const char *v15; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v16[2]; // [rsp+28h] [rbp-40h] BYREF
  _QWORD v17[6]; // [rsp+38h] [rbp-30h] BYREF
  unsigned __int64 v18; // [rsp+B8h] [rbp+50h] BYREF

  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           a1,
                           a1)
    || !a1
    || !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           v6,
                           a1)
    || (*((_BYTE *)a1 + 32) & 1) != 0 )
  {
    return 6;
  }
  if ( !AreAnyAccessesGranted(*((_DWORD *)a1 + 80), 0x10000003u) )
    return 5;
  v18 = 0;
  LODWORD(result) = StringCchLengthW(a2, 0x40u, &v18);
  v9 = result;
  if ( (int)result >= 0 )
  {
    v10 = v18 + 1;
    v11 = (wchar_t *)LocalAlloc(v8, 2 * (v18 + 1));
    v18 = (unsigned __int64)v11;
    v12 = v11;
    if ( v11 )
    {
      v14 = StringCchCopyW(v11, v10, a2);
      if ( v14 >= 0 )
      {
        if ( ClusterSupportsReasonString(a1) )
        {
          ClusterReason::ClusterReason((ClusterReason *)&v15, a1, a3);
          v17[1] = (char *)a1 + 40;
          v17[0] = "ApiSetClusterNameEx";
          v17[3] = v15;
          v17[2] = a2;
          v13 = ReconnectOnError<SetClusterNameExFunctor>(v17, a1);
          std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>(v16);
        }
        else
        {
          v16[0] = (char *)a1 + 40;
          v15 = "ApiSetClusterName";
          v16[1] = a2;
          v13 = ReconnectOnError<SetClusterNameFunctor>(&v15, a1);
        }
        if ( !v13 || v13 == 5024 )
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 232));
          LocalFree(*((HLOCAL *)a1 + 2));
          v18 = 0;
          *((_QWORD *)a1 + 2) = v12;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 232));
        }
      }
      else if ( (v14 & 0x1FFF0000) != 0x70000 || (v13 = (unsigned __int16)v14, !(_WORD)v14) )
      {
        v13 = v14;
      }
    }
    else
    {
      v13 = 8;
    }
    std::unique_ptr<wchar_t,MIDLDeleter>::~unique_ptr<wchar_t,MIDLDeleter>(&v18);
    return v13;
  }
  else
  {
    if ( (result & 0x1FFF0000) != 0x70000 )
      return v9;
    result = (unsigned __int16)result;
    if ( !(_WORD)v9 )
      return v9;
  }
  return result;
}

```

## disassembly

```asm
0x18002eaf0  push    rbp
0x18002eaf2  push    rbx
0x18002eaf3  push    rsi
0x18002eaf4  push    rdi
0x18002eaf5  push    r14
0x18002eaf7  push    r15
0x18002eaf9  mov     rbp, rsp
0x18002eafc  sub     rsp, 68h
0x18002eb00  mov     r14, rdx
0x18002eb03  mov     r15, r8
0x18002eb06  mov     rdx, rcx
0x18002eb09  mov     rsi, rcx
0x18002eb0c  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18002eb11  test    al, al
0x18002eb13  jz      loc_18002ECC1
0x18002eb19  test    rsi, rsi
0x18002eb1c  jz      loc_18002ECC1
0x18002eb22  mov     rdx, rsi
0x18002eb25  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18002eb2a  test    al, al
0x18002eb2c  jz      loc_18002ECC1
0x18002eb32  test    byte ptr [rsi+20h], 1
0x18002eb36  jnz     loc_18002ECC1
0x18002eb3c  mov     ecx, [rsi+140h]; GrantedAccess
0x18002eb42  mov     edx, 10000003h; DesiredAccess
0x18002eb47  call    cs:__imp_AreAnyAccessesGranted
0x18002eb4d  test    eax, eax
0x18002eb4f  jnz     short loc_18002EB5B
0x18002eb51  mov     eax, 5
0x18002eb56  jmp     loc_18002ECC6
0x18002eb5b  mov     r11d, 40h ; '@'
0x18002eb61  mov     [rbp+arg_18], 0
0x18002eb69  mov     edx, r11d; unsigned __int64
0x18002eb6c  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x18002eb70  mov     rcx, r14; wchar_t *
0x18002eb73  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x18002eb78  mov     r8d, eax
0x18002eb7b  test    eax, eax
0x18002eb7d  jns     short loc_18002EBA3
0x18002eb7f  mov     ecx, eax
0x18002eb81  and     ecx, 1FFF0000h
0x18002eb87  cmp     ecx, 70000h
0x18002eb8d  jnz     short loc_18002EB9B
0x18002eb8f  movzx   eax, r8w
0x18002eb93  test    eax, eax
0x18002eb95  jnz     loc_18002ECC6
0x18002eb9b  mov     eax, r8d
0x18002eb9e  jmp     loc_18002ECC6
0x18002eba3  mov     rdi, [rbp+arg_18]
0x18002eba7  mov     ecx, r11d; uFlags
0x18002ebaa  inc     rdi
0x18002ebad  lea     rdx, [rdi+rdi]; uBytes
0x18002ebb1  call    cs:__imp_LocalAlloc
0x18002ebb7  mov     [rbp+arg_18], rax
0x18002ebbb  mov     rbx, rax
0x18002ebbe  test    rax, rax
0x18002ebc1  jnz     short loc_18002EBCC
0x18002ebc3  lea     r14d, [rax+8]
0x18002ebc7  jmp     loc_18002ECB3
0x18002ebcc  mov     r8, r14; wchar_t *
0x18002ebcf  mov     rdx, rdi; unsigned __int64
0x18002ebd2  mov     rcx, rbx; wchar_t *
0x18002ebd5  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002ebda  test    eax, eax
0x18002ebdc  jns     short loc_18002EC03
0x18002ebde  mov     ecx, eax
0x18002ebe0  and     ecx, 1FFF0000h
0x18002ebe6  cmp     ecx, 70000h
0x18002ebec  jnz     short loc_18002EBFB
0x18002ebee  movzx   r14d, ax
0x18002ebf2  test    r14d, r14d
0x18002ebf5  jnz     loc_18002ECB3
0x18002ebfb  mov     r14d, eax
0x18002ebfe  jmp     loc_18002ECB3
0x18002ec03  mov     rcx, rsi; struct _CLUSTER *
0x18002ec06  lea     rdi, [rsi+28h]
0x18002ec0a  call    ?ClusterSupportsReasonString@@YA_NQEBU_CLUSTER@@@Z; ClusterSupportsReasonString(_CLUSTER const * const)
0x18002ec0f  mov     rdx, rsi; struct _HCLUSTER *
0x18002ec12  test    al, al
0x18002ec14  jz      short loc_18002EC57
0x18002ec16  mov     r8, r15; wchar_t *
0x18002ec19  lea     rcx, [rbp+var_48]; this
0x18002ec1d  call    ??0ClusterReason@@QEAA@PEAU_HCLUSTER@@PEB_W@Z; ClusterReason::ClusterReason(_HCLUSTER *,wchar_t const *)
0x18002ec22  lea     rax, aApisetclustern; "ApiSetClusterNameEx"
0x18002ec29  mov     [rbp+var_28], rdi
0x18002ec2d  mov     [rbp+var_30], rax
0x18002ec31  lea     rcx, [rbp+var_30]
0x18002ec35  mov     rax, [rbp+var_48]
0x18002ec39  mov     rdx, rsi
0x18002ec3c  mov     [rbp+var_18], rax
0x18002ec40  mov     [rbp+var_20], r14
0x18002ec44  call    ??$ReconnectOnError@VSetClusterNameExFunctor@@@@YAKAEAVSetClusterNameExFunctor@@PEAU_CLUSTER@@@Z; ReconnectOnError<SetClusterNameExFunctor>(SetClusterNameExFunctor &,_CLUSTER *)
0x18002ec49  lea     rcx, [rbp+var_40]
0x18002ec4d  mov     r14d, eax
0x18002ec50  call    ??1?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@std@@@std@@QEAA@XZ; std::unique_ptr<wchar_t [0]>::~unique_ptr<wchar_t [0]>(void)
0x18002ec55  jmp     short loc_18002EC76
0x18002ec57  lea     rax, aApisetclustern_0; "ApiSetClusterName"
0x18002ec5e  mov     [rbp+var_40], rdi
0x18002ec62  lea     rcx, [rbp+var_48]
0x18002ec66  mov     [rbp+var_48], rax
0x18002ec6a  mov     [rbp+var_38], r14
0x18002ec6e  call    ??$ReconnectOnError@VSetClusterNameFunctor@@@@YAKAEAVSetClusterNameFunctor@@PEAU_CLUSTER@@@Z; ReconnectOnError<SetClusterNameFunctor>(SetClusterNameFunctor &,_CLUSTER *)
0x18002ec73  mov     r14d, eax
0x18002ec76  test    r14d, r14d
0x18002ec79  jz      short loc_18002EC84
0x18002ec7b  cmp     r14d, 13A0h
0x18002ec82  jnz     short loc_18002ECB3
0x18002ec84  lea     rdi, [rsi+0E8h]
0x18002ec8b  mov     rcx, rdi; lpCriticalSection
0x18002ec8e  call    cs:__imp_EnterCriticalSection
0x18002ec94  mov     rcx, [rsi+10h]; hMem
0x18002ec98  call    cs:__imp_LocalFree
0x18002ec9e  mov     rcx, rdi; lpCriticalSection
0x18002eca1  mov     [rbp+arg_18], 0
0x18002eca9  mov     [rsi+10h], rbx
0x18002ecad  call    cs:__imp_LeaveCriticalSection
0x18002ecb3  lea     rcx, [rbp+arg_18]
0x18002ecb7  call    ??1?$unique_ptr@_WUMIDLDeleter@@@std@@QEAA@XZ; std::unique_ptr<wchar_t,MIDLDeleter>::~unique_ptr<wchar_t,MIDLDeleter>(void)
0x18002ecbc  mov     eax, r14d
0x18002ecbf  jmp     short loc_18002ECC6
0x18002ecc1  mov     eax, 6
0x18002ecc6  add     rsp, 68h
0x18002ecca  pop     r15
0x18002eccc  pop     r14
0x18002ecce  pop     rdi
0x18002eccf  pop     rsi
0x18002ecd0  pop     rbx
0x18002ecd1  pop     rbp
0x18002ecd2  retn
```
