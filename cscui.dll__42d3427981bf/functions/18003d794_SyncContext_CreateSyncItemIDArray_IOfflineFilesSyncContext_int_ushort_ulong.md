# SyncContext_CreateSyncItemIDArray(IOfflineFilesSyncContext *,int,ushort * * *,ulong *)

- ea: `0x18003d794`
- end: `0x18003d99b`
- name: `?SyncContext_CreateSyncItemIDArray@@YAJPEAUIOfflineFilesSyncContext@@HPEAPEAPEAGPEAK@Z`
- size: `519`
- prototype: `__int64 __fastcall(struct IOfflineFilesSyncContext *, int, unsigned __int16 ***, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800195f0`
- `0x180022e70`

## callees

- `0x18001101c`
- `0x18003be8c`
- `0x18003c218`
- `0x18003c488`
- `0x18003c6a0`
- `0x18003d794`
- `0x18004a870`
- `0x18004a934`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d8d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d8d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d889`

## pseudocode

```c
__int64 __fastcall SyncContext_CreateSyncItemIDArray(
        struct IOfflineFilesSyncContext *a1,
        int a2,
        unsigned __int16 ***a3,
        unsigned int *a4)
{
  unsigned int v4; // r12d
  unsigned __int16 ***v6; // r13
  int appended; // esi
  __int64 v9; // rax
  struct _DPA *v10; // rbx
  unsigned int v11; // r14d
  unsigned __int16 **v12; // r15
  int v14; // [rsp+30h] [rbp-30h] BYREF
  int v15; // [rsp+34h] [rbp-2Ch] BYREF
  HDPA hdpa; // [rsp+38h] [rbp-28h] BYREF
  __int64 v17; // [rsp+40h] [rbp-20h] BYREF
  __int64 v18; // [rsp+48h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-10h] BYREF

  v4 = 0;
  *a4 = 0;
  *a3 = 0;
  v6 = a3;
  hdpa = 0;
  appended = -2147024882;
  if ( !(unsigned int)CDPA_Base<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::Create(&hdpa) )
    goto LABEL_24;
  v9 = *(_QWORD *)a1;
  v18 = 0;
  appended = (*(__int64 (__fastcall **)(struct IOfflineFilesSyncContext *, __int64 *))(v9 + 64))(a1, &v18);
  if ( appended >= 0 )
  {
    v17 = 0;
    v15 = 0;
    do
    {
      appended = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v18 + 24LL))(
                   v18,
                   1,
                   &v17,
                   &v15);
      if ( appended )
        break;
      v14 = 0;
      appended = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v17 + 40LL))(v17, &v14);
      if ( appended >= 0 && (!a2 || !v14) )
      {
        pv[0] = 0;
        appended = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v17 + 24LL))(v17, pv);
        if ( appended >= 0 )
        {
          appended = CDPA_Base<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::AppendPtr(&hdpa, pv[0]);
          if ( appended < 0 )
            CoTaskMemFree(pv[0]);
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    while ( appended >= 0 );
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
    if ( appended >= 0 )
    {
      v10 = hdpa;
      if ( hdpa && (v11 = *(_DWORD *)hdpa) != 0 )
      {
        v12 = (unsigned __int16 **)CoTaskMemAlloc(8LL * v11);
        if ( v12 )
        {
          appended = 0;
          if ( v11 )
          {
            do
            {
              v12[v4] = (unsigned __int16 *)DPA_GetPtr(v10, v4);
              ++*a4;
              DPA_SetPtr(v10, v4++, 0);
            }
            while ( v4 < v11 );
            v6 = a3;
          }
          *v6 = v12;
        }
        else
        {
          appended = -2147024882;
        }
      }
      else
      {
        appended = -2147024637;
      }
    }
  }
  CDPA_Base<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::DestroyCallback(
    &hdpa,
    SyncContext_DestroyComString);
  if ( appended < 0 )
  {
LABEL_24:
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_f72d3c378080343ef5b9ab31099f269e_Traceguids,
        (unsigned int)appended);
    }
  }
  CDPA_Base<CSyncContextItem,CTContainer_PolicyUnOwned<CSyncContextItem>>::~CDPA_Base<CSyncContextItem,CTContainer_PolicyUnOwned<CSyncContextItem>>(&hdpa);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18003d794  mov     [rsp-38h+arg_0], rbx
0x18003d799  mov     [rsp-38h+arg_18], r9
0x18003d79e  mov     [rsp-38h+arg_10], r8
0x18003d7a3  push    rbp
0x18003d7a4  push    rsi
0x18003d7a5  push    rdi
0x18003d7a6  push    r12
0x18003d7a8  push    r13
0x18003d7aa  push    r14
0x18003d7ac  push    r15
0x18003d7ae  mov     rbp, rsp
0x18003d7b1  sub     rsp, 60h
0x18003d7b5  xor     r12d, r12d
0x18003d7b8  mov     rbx, rcx
0x18003d7bb  mov     [r9], r12d
0x18003d7be  lea     rcx, [rbp+hdpa]
0x18003d7c2  mov     [r8], r12
0x18003d7c5  mov     r13, r8
0x18003d7c8  mov     edi, edx
0x18003d7ca  mov     [rbp+hdpa], r12
0x18003d7ce  mov     esi, 8007000Eh
0x18003d7d3  call    ?Create@?$CDPA_Base@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAHH@Z; CDPA_Base<ushort,CTContainer_PolicyUnOwned<ushort>>::Create(int)
0x18003d7d8  test    eax, eax
0x18003d7da  jz      loc_18003D947
0x18003d7e0  mov     rax, [rbx]
0x18003d7e3  lea     rdx, [rbp+var_18]
0x18003d7e7  mov     rcx, rbx
0x18003d7ea  mov     [rbp+var_18], r12
0x18003d7ee  mov     rax, [rax+40h]
0x18003d7f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7f7  mov     esi, eax
0x18003d7f9  test    eax, eax
0x18003d7fb  js      loc_18003D933
0x18003d801  mov     [rbp+var_20], r12
0x18003d805  mov     [rbp+var_2C], r12d
0x18003d809  mov     rcx, [rbp+var_18]
0x18003d80d  lea     r9, [rbp+var_2C]
0x18003d811  lea     r8, [rbp+var_20]
0x18003d815  mov     edx, 1
0x18003d81a  mov     rax, [rcx]
0x18003d81d  mov     rax, [rax+18h]
0x18003d821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d826  mov     esi, eax
0x18003d828  test    eax, eax
0x18003d82a  jnz     short loc_18003D8A7
0x18003d82c  mov     rcx, [rbp+var_20]
0x18003d830  lea     rdx, [rbp+var_30]
0x18003d834  mov     [rbp+var_30], r12d
0x18003d838  mov     rax, [rcx]
0x18003d83b  mov     rax, [rax+28h]
0x18003d83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d844  mov     esi, eax
0x18003d846  test    eax, eax
0x18003d848  js      short loc_18003D88F
0x18003d84a  test    edi, edi
0x18003d84c  jz      short loc_18003D854
0x18003d84e  cmp     [rbp+var_30], r12d
0x18003d852  jnz     short loc_18003D88F
0x18003d854  mov     rcx, [rbp+var_20]
0x18003d858  lea     rdx, [rbp+pv]
0x18003d85c  mov     [rbp+pv], r12
0x18003d860  mov     rax, [rcx]
0x18003d863  mov     rax, [rax+18h]
0x18003d867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d86c  mov     esi, eax
0x18003d86e  test    eax, eax
0x18003d870  js      short loc_18003D88F
0x18003d872  mov     rdx, [rbp+pv]
0x18003d876  lea     rcx, [rbp+hdpa]
0x18003d87a  call    ?AppendPtr@?$CDPA_Base@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAJPEAGPEAH@Z; CDPA_Base<ushort,CTContainer_PolicyUnOwned<ushort>>::AppendPtr(ushort *,int *)
0x18003d87f  mov     esi, eax
0x18003d881  test    eax, eax
0x18003d883  jns     short loc_18003D88F
0x18003d885  mov     rcx, [rbp+pv]; pv
0x18003d889  call    cs:__imp_CoTaskMemFree
0x18003d88f  mov     rcx, [rbp+var_20]
0x18003d893  mov     rax, [rcx]
0x18003d896  mov     rax, [rax+10h]
0x18003d89a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d89f  test    esi, esi
0x18003d8a1  jns     loc_18003D809
0x18003d8a7  mov     rcx, [rbp+var_18]
0x18003d8ab  mov     rax, [rcx]
0x18003d8ae  mov     rax, [rax+10h]
0x18003d8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8b7  mov     [rbp+var_18], r12
0x18003d8bb  test    esi, esi
0x18003d8bd  js      short loc_18003D933
0x18003d8bf  mov     rbx, [rbp+hdpa]
0x18003d8c3  test    rbx, rbx
0x18003d8c6  jz      short loc_18003D92E
0x18003d8c8  mov     r14d, [rbx]
0x18003d8cb  test    r14d, r14d
0x18003d8ce  jz      short loc_18003D92E
0x18003d8d0  mov     ecx, r14d
0x18003d8d3  shl     rcx, 3; cb
0x18003d8d7  call    cs:__imp_CoTaskMemAlloc
0x18003d8dd  mov     r15, rax
0x18003d8e0  test    rax, rax
0x18003d8e3  jnz     short loc_18003D8EC
0x18003d8e5  mov     esi, 8007000Eh
0x18003d8ea  jmp     short loc_18003D933
0x18003d8ec  mov     esi, r12d
0x18003d8ef  test    r14d, r14d
0x18003d8f2  jz      short loc_18003D928
0x18003d8f4  mov     r13, [rbp+arg_18]
0x18003d8f8  mov     edx, r12d; i
0x18003d8fb  mov     rcx, rbx; hdpa
0x18003d8fe  mov     edi, r12d
0x18003d901  call    DPA_GetPtr
0x18003d906  mov     [r15+rdi*8], rax
0x18003d90a  xor     r8d, r8d; p
0x18003d90d  inc     dword ptr [r13+0]
0x18003d911  mov     edx, r12d; i
0x18003d914  mov     rcx, rbx; hdpa
0x18003d917  call    DPA_SetPtr
0x18003d91c  inc     r12d
0x18003d91f  cmp     r12d, r14d
0x18003d922  jb      short loc_18003D8F8
0x18003d924  mov     r13, [rbp+arg_10]
0x18003d928  mov     [r13+0], r15
0x18003d92c  jmp     short loc_18003D933
0x18003d92e  mov     esi, 80070103h
0x18003d933  lea     rdx, ?SyncContext_DestroyComString@@YAHPEAGPEAX@Z; SyncContext_DestroyComString(ushort *,void *)
0x18003d93a  lea     rcx, [rbp+hdpa]
0x18003d93e  call    ?DestroyCallback@?$CDPA_Base@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAXP6AHPEAGPEAX@Z1@Z; CDPA_Base<ushort,CTContainer_PolicyUnOwned<ushort>>::DestroyCallback(int (*)(ushort *,void *),void *)
0x18003d943  test    esi, esi
0x18003d945  jns     short loc_18003D978
0x18003d947  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d94e  lea     rax, WPP_GLOBAL_Control
0x18003d955  cmp     rcx, rax
0x18003d958  jz      short loc_18003D978
0x18003d95a  test    byte ptr [rcx+1Ch], 2
0x18003d95e  jz      short loc_18003D978
0x18003d960  mov     rcx, [rcx+10h]
0x18003d964  lea     r8, WPP_f72d3c378080343ef5b9ab31099f269e_Traceguids
0x18003d96b  mov     edx, 1Dh
0x18003d970  mov     r9d, esi
0x18003d973  call    WPP_SF_d
0x18003d978  lea     rcx, [rbp+hdpa]
0x18003d97c  call    ??1?$CDPA_Base@VCSyncContextItem@@V?$CTContainer_PolicyUnOwned@VCSyncContextItem@@@@@@QEAA@XZ; CDPA_Base<CSyncContextItem,CTContainer_PolicyUnOwned<CSyncContextItem>>::~CDPA_Base<CSyncContextItem,CTContainer_PolicyUnOwned<CSyncContextItem>>(void)
0x18003d981  mov     rbx, [rsp+60h+arg_0]
0x18003d989  mov     eax, esi
0x18003d98b  add     rsp, 60h
0x18003d98f  pop     r15
0x18003d991  pop     r14
0x18003d993  pop     r13
0x18003d995  pop     r12
0x18003d997  pop     rdi
0x18003d998  pop     rsi
0x18003d999  pop     rbp
0x18003d99a  retn
```
