# SyncContext_CreateSyncItemPathArray(IOfflineFilesSyncContextItem *,ushort * * *,ulong *)

- ea: `0x18003d9a4`
- end: `0x18003db8b`
- name: `?SyncContext_CreateSyncItemPathArray@@YAJPEAUIOfflineFilesSyncContextItem@@PEAPEAPEAGPEAK@Z`
- size: `487`
- prototype: `__int64 __fastcall(struct IOfflineFilesSyncContextItem *, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001ac68`

## callees

- `0x18001101c`
- `0x18003be8c`
- `0x18003c218`
- `0x18003c488`
- `0x18003c6a0`
- `0x18003d9a4`
- `0x18004a870`
- `0x18004a934`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003dad1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003dad1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003da51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003da51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dab5`

## pseudocode

```c
__int64 __fastcall SyncContext_CreateSyncItemPathArray(
        struct IOfflineFilesSyncContextItem *a1,
        unsigned __int16 ***a2,
        unsigned int *a3)
{
  unsigned int v3; // r12d
  unsigned __int16 ***v5; // r13
  int appended; // esi
  __int64 v7; // rax
  HDPA v8; // rbx
  unsigned int v9; // r14d
  unsigned __int16 **v10; // r15
  unsigned __int16 *Ptr; // rax
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  HDPA hdpa; // [rsp+38h] [rbp-18h] BYREF
  __int64 v15; // [rsp+40h] [rbp-10h] BYREF
  int v18; // [rsp+A8h] [rbp+58h] BYREF

  v3 = 0;
  *a3 = 0;
  *a2 = 0;
  v5 = a2;
  hdpa = 0;
  appended = -2147024882;
  if ( (unsigned int)CDPA_Base<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::Create(&hdpa) )
  {
    v7 = *(_QWORD *)a1;
    pv = 0;
    v18 = 0;
    v15 = 0;
    appended = (*(__int64 (__fastcall **)(struct IOfflineFilesSyncContextItem *, __int64 *))(v7 + 48))(a1, &v15);
    if ( appended >= 0 )
    {
      while ( 1 )
      {
        appended = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v15 + 24LL))(
                     v15,
                     1,
                     &pv,
                     &v18);
        if ( appended )
          break;
        appended = CDPA_Base<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::AppendPtr(&hdpa, pv);
        if ( appended < 0 )
        {
          CoTaskMemFree(pv);
          break;
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v15 = 0;
      if ( appended >= 0 )
      {
        v8 = hdpa;
        if ( hdpa && *(_DWORD *)hdpa )
          goto LABEL_12;
        appended = (*(__int64 (__fastcall **)(struct IOfflineFilesSyncContextItem *, LPVOID *))(*(_QWORD *)a1 + 32LL))(
                     a1,
                     &pv);
        if ( appended < 0 )
          goto LABEL_21;
        appended = CDPA_Base<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::AppendPtr(&hdpa, pv);
        if ( appended >= 0 )
        {
LABEL_12:
          if ( v8 )
            v9 = *(_DWORD *)v8;
          else
            v9 = 0;
          v10 = (unsigned __int16 **)CoTaskMemAlloc(8LL * v9);
          if ( v10 )
          {
            if ( v9 )
            {
              do
              {
                Ptr = (unsigned __int16 *)DPA_GetPtr(v8, v3);
                ++*a3;
                v10[v3] = Ptr;
                DPA_SetPtr(v8, v3++, 0);
              }
              while ( v3 < v9 );
              v5 = a2;
            }
            *v5 = v10;
          }
          else
          {
            appended = -2147024882;
          }
        }
        else
        {
          CoTaskMemFree(pv);
        }
      }
    }
LABEL_21:
    CDPA_Base<unsigned short,CTContainer_PolicyUnOwned<unsigned short>>::DestroyCallback(
      &hdpa,
      SyncContext_DestroyComString);
    if ( appended >= 0 )
      goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      WPP_f72d3c378080343ef5b9ab31099f269e_Traceguids,
      (unsigned int)appended);
  }
LABEL_25:
  CDPA_Base<CSyncContextItem,CTContainer_PolicyUnOwned<CSyncContextItem>>::~CDPA_Base<CSyncContextItem,CTContainer_PolicyUnOwned<CSyncContextItem>>(&hdpa);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18003d9a4  mov     [rsp-38h+arg_0], rbx
0x18003d9a9  mov     [rsp-38h+arg_10], r8
0x18003d9ae  mov     [rsp-38h+arg_8], rdx
0x18003d9b3  push    rbp
0x18003d9b4  push    rsi
0x18003d9b5  push    rdi
0x18003d9b6  push    r12
0x18003d9b8  push    r13
0x18003d9ba  push    r14
0x18003d9bc  push    r15
0x18003d9be  mov     rbp, rsp
0x18003d9c1  sub     rsp, 50h
0x18003d9c5  xor     r12d, r12d
0x18003d9c8  mov     rdi, rcx
0x18003d9cb  lea     rcx, [rbp+hdpa]
0x18003d9cf  mov     [r8], r12d
0x18003d9d2  mov     [rdx], r12
0x18003d9d5  mov     r13, rdx
0x18003d9d8  mov     [rbp+hdpa], r12
0x18003d9dc  mov     esi, 8007000Eh
0x18003d9e1  call    ?Create@?$CDPA_Base@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAHH@Z; CDPA_Base<ushort,CTContainer_PolicyUnOwned<ushort>>::Create(int)
0x18003d9e6  test    eax, eax
0x18003d9e8  jz      loc_18003DB37
0x18003d9ee  mov     rax, [rdi]
0x18003d9f1  lea     rdx, [rbp+var_10]
0x18003d9f5  mov     rcx, rdi
0x18003d9f8  mov     [rbp+pv], r12
0x18003d9fc  mov     [rbp+arg_18], r12d
0x18003da00  mov     [rbp+var_10], r12
0x18003da04  mov     rax, [rax+30h]
0x18003da08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da0d  mov     esi, eax
0x18003da0f  test    eax, eax
0x18003da11  js      loc_18003DB23
0x18003da17  mov     rcx, [rbp+var_10]
0x18003da1b  lea     r9, [rbp+arg_18]
0x18003da1f  lea     r8, [rbp+pv]
0x18003da23  mov     edx, 1
0x18003da28  mov     rax, [rcx]
0x18003da2b  mov     rax, [rax+18h]
0x18003da2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da34  mov     esi, eax
0x18003da36  test    eax, eax
0x18003da38  jnz     short loc_18003DA57
0x18003da3a  mov     rdx, [rbp+pv]
0x18003da3e  lea     rcx, [rbp+hdpa]
0x18003da42  call    ?AppendPtr@?$CDPA_Base@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAJPEAGPEAH@Z; CDPA_Base<ushort,CTContainer_PolicyUnOwned<ushort>>::AppendPtr(ushort *,int *)
0x18003da47  mov     esi, eax
0x18003da49  test    eax, eax
0x18003da4b  jns     short loc_18003DA17
0x18003da4d  mov     rcx, [rbp+pv]; pv
0x18003da51  call    cs:__imp_CoTaskMemFree
0x18003da57  mov     rcx, [rbp+var_10]
0x18003da5b  mov     rax, [rcx]
0x18003da5e  mov     rax, [rax+10h]
0x18003da62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da67  mov     [rbp+var_10], r12
0x18003da6b  test    esi, esi
0x18003da6d  js      loc_18003DB23
0x18003da73  mov     rbx, [rbp+hdpa]
0x18003da77  test    rbx, rbx
0x18003da7a  jz      short loc_18003DA81
0x18003da7c  cmp     [rbx], r12d
0x18003da7f  jnz     short loc_18003DABD
0x18003da81  mov     rax, [rdi]
0x18003da84  lea     rdx, [rbp+pv]
0x18003da88  mov     rcx, rdi
0x18003da8b  mov     rax, [rax+20h]
0x18003da8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da94  mov     esi, eax
0x18003da96  test    eax, eax
0x18003da98  js      loc_18003DB23
0x18003da9e  mov     rdx, [rbp+pv]
0x18003daa2  lea     rcx, [rbp+hdpa]
0x18003daa6  call    ?AppendPtr@?$CDPA_Base@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAJPEAGPEAH@Z; CDPA_Base<ushort,CTContainer_PolicyUnOwned<ushort>>::AppendPtr(ushort *,int *)
0x18003daab  mov     esi, eax
0x18003daad  test    eax, eax
0x18003daaf  jns     short loc_18003DABD
0x18003dab1  mov     rcx, [rbp+pv]; pv
0x18003dab5  call    cs:__imp_CoTaskMemFree
0x18003dabb  jmp     short loc_18003DB23
0x18003dabd  test    rbx, rbx
0x18003dac0  jz      short loc_18003DAC7
0x18003dac2  mov     r14d, [rbx]
0x18003dac5  jmp     short loc_18003DACA
0x18003dac7  mov     r14d, r12d
0x18003daca  mov     ecx, r14d
0x18003dacd  shl     rcx, 3; cb
0x18003dad1  call    cs:__imp_CoTaskMemAlloc
0x18003dad7  mov     r15, rax
0x18003dada  test    rax, rax
0x18003dadd  jnz     short loc_18003DAE6
0x18003dadf  mov     esi, 8007000Eh
0x18003dae4  jmp     short loc_18003DB23
0x18003dae6  test    r14d, r14d
0x18003dae9  jz      short loc_18003DB1F
0x18003daeb  mov     r13, [rbp+arg_10]
0x18003daef  mov     edx, r12d; i
0x18003daf2  mov     rcx, rbx; hdpa
0x18003daf5  mov     edi, r12d
0x18003daf8  call    DPA_GetPtr
0x18003dafd  inc     dword ptr [r13+0]
0x18003db01  xor     r8d, r8d; p
0x18003db04  mov     edx, r12d; i
0x18003db07  mov     [r15+rdi*8], rax
0x18003db0b  mov     rcx, rbx; hdpa
0x18003db0e  call    DPA_SetPtr
0x18003db13  inc     r12d
0x18003db16  cmp     r12d, r14d
0x18003db19  jb      short loc_18003DAEF
0x18003db1b  mov     r13, [rbp+arg_8]
0x18003db1f  mov     [r13+0], r15
0x18003db23  lea     rdx, ?SyncContext_DestroyComString@@YAHPEAGPEAX@Z; SyncContext_DestroyComString(ushort *,void *)
0x18003db2a  lea     rcx, [rbp+hdpa]
0x18003db2e  call    ?DestroyCallback@?$CDPA_Base@GV?$CTContainer_PolicyUnOwned@G@@@@QEAAXP6AHPEAGPEAX@Z1@Z; CDPA_Base<ushort,CTContainer_PolicyUnOwned<ushort>>::DestroyCallback(int (*)(ushort *,void *),void *)
0x18003db33  test    esi, esi
0x18003db35  jns     short loc_18003DB68
0x18003db37  mov     rcx, cs:WPP_GLOBAL_Control
0x18003db3e  lea     rax, WPP_GLOBAL_Control
0x18003db45  cmp     rcx, rax
0x18003db48  jz      short loc_18003DB68
0x18003db4a  test    byte ptr [rcx+1Ch], 2
0x18003db4e  jz      short loc_18003DB68
0x18003db50  mov     rcx, [rcx+10h]
0x18003db54  lea     r8, WPP_f72d3c378080343ef5b9ab31099f269e_Traceguids
0x18003db5b  mov     edx, 1Eh
0x18003db60  mov     r9d, esi
0x18003db63  call    WPP_SF_d
0x18003db68  lea     rcx, [rbp+hdpa]
0x18003db6c  call    ??1?$CDPA_Base@VCSyncContextItem@@V?$CTContainer_PolicyUnOwned@VCSyncContextItem@@@@@@QEAA@XZ; CDPA_Base<CSyncContextItem,CTContainer_PolicyUnOwned<CSyncContextItem>>::~CDPA_Base<CSyncContextItem,CTContainer_PolicyUnOwned<CSyncContextItem>>(void)
0x18003db71  mov     rbx, [rsp+50h+arg_0]
0x18003db79  mov     eax, esi
0x18003db7b  add     rsp, 50h
0x18003db7f  pop     r15
0x18003db81  pop     r14
0x18003db83  pop     r13
0x18003db85  pop     r12
0x18003db87  pop     rdi
0x18003db88  pop     rsi
0x18003db89  pop     rbp
0x18003db8a  retn
```
