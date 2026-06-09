# InitializeClusterNotifyPort(_HCHANGE *,_HCLUSTER *,CLUSTER_NOTIFICATIONS_VERSION const &,_CNOTIFY * &,int &)

- ea: `0x18005cbb4`
- end: `0x18005cce1`
- name: `?InitializeClusterNotifyPort@@YAKPEAU_HCHANGE@@PEAU_HCLUSTER@@AEBW4CLUSTER_NOTIFICATIONS_VERSION@@AEAPEAU_CNOTIFY@@AEAH@Z`
- size: `301`
- prototype: `unsigned int __fastcall(struct _HCHANGE *, struct _HCLUSTER *, const enum CLUSTER_NOTIFICATIONS_VERSION *, struct _CNOTIFY **, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005e840`
- `0x18005ea10`

## callees

- `0x180014638`
- `0x18005987c`
- `0x1800598dc`
- `0x18005c424`
- `0x18005cbb4`
- `0x18009e238`
- `0x1800a2f18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18005cc0c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18005cc0c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005cc34`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005cc34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005cc4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ccc8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005cc4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ccc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cc3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005cc3d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005cbdb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005cbdb`

## pseudocode

```c
__int64 __fastcall InitializeClusterNotifyPort(
        struct _HCHANGE *a1,
        struct _HCLUSTER *a2,
        const enum CLUSTER_NOTIFICATIONS_VERSION *a3,
        HLOCAL *a4,
        int *a5)
{
  _QWORD *v9; // rax
  _QWORD *v10; // rcx
  DWORD v11; // ebx
  _QWORD *v12; // rax
  _DWORD *v13; // rcx
  DWORD v14; // eax
  _DWORD *v15; // rcx
  DWORD v16; // esi
  __int64 v18; // rcx
  __int64 v19; // rcx

  if ( a1 != (struct _HCHANGE *)-1LL )
  {
    *a4 = a1;
    if ( (unsigned __int64)a2 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      goto LABEL_16;
    if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                             a1,
                             a2)
      || !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCHANGE *>(
                             v19,
                             a1) )
    {
      v11 = 6;
      goto LABEL_17;
    }
    if ( *((_DWORD *)*a4 + 194) != *(_DWORD *)a3 )
    {
LABEL_16:
      v11 = 87;
      goto LABEL_17;
    }
    return 0;
  }
  v9 = LocalAlloc(0, 0x310u);
  *a4 = v9;
  v10 = v9;
  if ( v9 )
  {
    v9[1] = v9;
    *v9 = v9;
    v12 = v9 + 95;
    v12[1] = v12;
    *v12 = v12;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v10 + 2));
    v13 = *a4;
    v13[194] = *(_DWORD *)a3;
    v14 = ClRtlInitializeQueue((__int64)(v13 + 14));
    v15 = *a4;
    v16 = v14;
    if ( v14 )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)(v15 + 4));
      LocalFree(*a4);
LABEL_6:
      *a4 = 0;
      SetLastError(v16);
      return v16;
    }
    ClRtlInitializeHash((LPCRITICAL_SECTION)(v15 + 34));
    v16 = HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Insert<_HCHANGE *>(
            v18,
            *a4);
    if ( v16 )
    {
      DestroyNotifyCommon((char *)*a4, 0);
      goto LABEL_6;
    }
    if ( a2 == (struct _HCLUSTER *)-1LL )
      *a5 = 1;
    return 0;
  }
  v11 = 8;
LABEL_17:
  SetLastError(v11);
  return v11;
}

```

## disassembly

```asm
0x18005cbb4  push    rbx
0x18005cbb6  push    rsi
0x18005cbb7  push    rdi
0x18005cbb8  push    r14
0x18005cbba  sub     rsp, 28h
0x18005cbbe  mov     rbx, r9
0x18005cbc1  mov     r14, r8
0x18005cbc4  mov     rdi, rdx
0x18005cbc7  mov     rsi, rcx
0x18005cbca  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005cbce  jnz     loc_18005CC91
0x18005cbd4  mov     edx, 310h; uBytes
0x18005cbd9  xor     ecx, ecx; uFlags
0x18005cbdb  call    cs:__imp_LocalAlloc
0x18005cbe1  mov     [rbx], rax
0x18005cbe4  mov     rcx, rax
0x18005cbe7  test    rax, rax
0x18005cbea  jnz     short loc_18005CBF4
0x18005cbec  lea     ebx, [rsi+9]
0x18005cbef  jmp     loc_18005CCC6
0x18005cbf4  mov     [rax+8], rcx
0x18005cbf8  mov     [rax], rcx
0x18005cbfb  add     rax, 2F8h
0x18005cc01  add     rcx, 10h; lpCriticalSection
0x18005cc05  mov     [rax+8], rax
0x18005cc09  mov     [rax], rax
0x18005cc0c  call    cs:__imp_InitializeCriticalSection
0x18005cc12  mov     rcx, [rbx]
0x18005cc15  mov     eax, [r14]
0x18005cc18  mov     [rcx+308h], eax
0x18005cc1e  add     rcx, 38h ; '8'
0x18005cc22  call    ClRtlInitializeQueue
0x18005cc27  mov     rcx, [rbx]
0x18005cc2a  mov     esi, eax
0x18005cc2c  test    eax, eax
0x18005cc2e  jz      short loc_18005CC56
0x18005cc30  add     rcx, 10h; lpCriticalSection
0x18005cc34  call    cs:__imp_DeleteCriticalSection
0x18005cc3a  mov     rcx, [rbx]; hMem
0x18005cc3d  call    cs:__imp_LocalFree
0x18005cc43  mov     ecx, esi; dwErrCode
0x18005cc45  mov     qword ptr [rbx], 0
0x18005cc4c  call    cs:__imp_SetLastError
0x18005cc52  mov     eax, esi
0x18005cc54  jmp     short loc_18005CCD0
0x18005cc56  add     rcx, 88h; lpCriticalSection
0x18005cc5d  call    ClRtlInitializeHash
0x18005cc62  mov     rdx, [rbx]
0x18005cc65  call    ??$Insert@PEAU_HCHANGE@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAAKPEAU_HCHANGE@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Insert<_HCHANGE *>(_HCHANGE *)
0x18005cc6a  mov     esi, eax
0x18005cc6c  test    eax, eax
0x18005cc6e  jz      short loc_18005CC7C
0x18005cc70  mov     rcx, [rbx]; hMem
0x18005cc73  xor     edx, edx; int
0x18005cc75  call    ?DestroyNotifyCommon@@YAXPEAU_CNOTIFY@@H@Z; DestroyNotifyCommon(_CNOTIFY *,int)
0x18005cc7a  jmp     short loc_18005CC43
0x18005cc7c  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18005cc80  jnz     short loc_18005CC8D
0x18005cc82  mov     rax, [rsp+48h+arg_20]
0x18005cc87  mov     dword ptr [rax], 1
0x18005cc8d  xor     eax, eax
0x18005cc8f  jmp     short loc_18005CCD0
0x18005cc91  lea     rax, [rdx-1]
0x18005cc95  mov     [r9], rsi
0x18005cc98  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005cc9c  ja      short loc_18005CCC1
0x18005cc9e  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18005cca3  test    al, al
0x18005cca5  jz      short loc_18005CCDA
0x18005cca7  mov     rdx, rsi
0x18005ccaa  call    ??$Contains@PEAU_HCHANGE@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCHANGE@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCHANGE *>(_HCHANGE *)
0x18005ccaf  test    al, al
0x18005ccb1  jz      short loc_18005CCDA
0x18005ccb3  mov     rcx, [rbx]
0x18005ccb6  mov     eax, [r14]
0x18005ccb9  cmp     [rcx+308h], eax
0x18005ccbf  jz      short loc_18005CC8D
0x18005ccc1  mov     ebx, 57h ; 'W'
0x18005ccc6  mov     ecx, ebx; dwErrCode
0x18005ccc8  call    cs:__imp_SetLastError
0x18005ccce  mov     eax, ebx
0x18005ccd0  add     rsp, 28h
0x18005ccd4  pop     r14
0x18005ccd6  pop     rdi
0x18005ccd7  pop     rsi
0x18005ccd8  pop     rbx
0x18005ccd9  retn
0x18005ccda  mov     ebx, 6
0x18005ccdf  jmp     short loc_18005CCC6
```
