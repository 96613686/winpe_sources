# W3_SERVER::GetWorkerProcessInfo(ushort const *,ushort const *,ICustomActionResultCallback *)

- ea: `0x18000aae0`
- end: `0x18000acf4`
- name: `?GetWorkerProcessInfo@W3_SERVER@@QEAAJPEBG0PEAVICustomActionResultCallback@@@Z`
- size: `532`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct ICustomActionResultCallback *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800312a0`

## callees

- `0x18000aae0`
- `0x18000ad00`
- `0x180014d00`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ac27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ace9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ac27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ace9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000acaf`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000acaf`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ab32`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ab49`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ab5a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ac57`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ab32`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ab49`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ab5a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000ac57`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ac36`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000ac36`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000acde`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000acde`

## pseudocode

```c
__int64 __fastcall W3_SERVER::GetWorkerProcessInfo(
        W3_SERVER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct ICustomActionResultCallback *a4)
{
  W3_SERVER *v4; // r14
  _QWORD *Ptr; // rax
  __int64 v7; // rbx
  _QWORD *v8; // rsi
  unsigned int *v9; // rbx
  VIRTUAL_MODULE **v10; // r15
  __int64 v11; // rax
  unsigned int v12; // ebx
  unsigned int v13; // eax
  HLOCAL v14; // rcx
  __int64 v16; // rdi
  int *v17; // rdi
  int i; // eax
  __int64 v19; // rcx
  _QWORD v20[3]; // [rsp+30h] [rbp-88h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-70h]
  __int64 v22; // [rsp+50h] [rbp-68h]
  int v23; // [rsp+58h] [rbp-60h]
  int v24; // [rsp+5Ch] [rbp-5Ch]
  FILETIME FileTime1; // [rsp+60h] [rbp-58h] BYREF

  v4 = g_pW3Server;
  v20[0] = &RSCA_QUERY_PROVIDER_CONTEXT::`vftable';
  v20[1] = a2;
  v20[2] = a3;
  hMem = 0;
  v22 = 0;
  v23 = -2147467263;
  v24 = 0;
  Ptr = BUFFER::QueryPtr((W3_SERVER *)((char *)g_pW3Server + 560));
  v7 = *((unsigned int *)v4 + 290);
  v8 = Ptr;
  v9 = (unsigned int *)((char *)BUFFER::QueryPtr((W3_SERVER *)((char *)v4 + 1056)) + 4 * v7);
  v10 = (VIRTUAL_MODULE **)BUFFER::QueryPtr((W3_SERVER *)((char *)v4 + 560));
  FileTime1 = 0;
  if ( *((_DWORD *)v4 + 396) )
  {
    CReaderWriterLock3::WriteLock((W3_SERVER *)((char *)v4 + 1588));
    if ( *((_DWORD *)v4 + 396) )
    {
      v16 = *((unsigned int *)v4 + 295);
      v17 = (int *)((char *)BUFFER::QueryPtr((W3_SERVER *)((char *)v4 + 1056)) + 4 * v16);
      for ( i = *v17; i != -1; ++v17 )
      {
        VIRTUAL_MODULE::Resume(v10[i]);
        i = v17[1];
      }
      v19 = *((_QWORD *)v4 + 187);
      if ( v19
        && (*(int (__fastcall **)(__int64, FILETIME *))(*(_QWORD *)v19 + 176LL))(v19, &FileTime1) >= 0
        && CompareFileTime(&FileTime1, (const FILETIME *)((char *)v4 + 1612)) == 1 )
      {
        (*(void (__fastcall **)(W3_SERVER *, const wchar_t *))(*(_QWORD *)v4 + 112LL))(v4, L"MACHINE/WEBROOT/APPHOST");
      }
      *((_DWORD *)v4 + 396) = 0;
    }
    CReaderWriterLock3::WriteUnlock((W3_SERVER *)((char *)v4 + 1588));
  }
  while ( 1 )
  {
    v11 = *v9;
    if ( (_DWORD)v11 == -1 || (unsigned int)VIRTUAL_MODULE::GlobalDoWork(v8[v11], 4096, v20) == 1 )
      break;
    ++v9;
  }
  v12 = v23;
  if ( v23 < 0 )
  {
    v14 = hMem;
    v20[0] = &RSCA_QUERY_PROVIDER_CONTEXT::`vftable';
    if ( !hMem )
      return v12;
    goto LABEL_13;
  }
  if ( v24 )
  {
    v13 = (*(__int64 (__fastcall **)(struct ICustomActionResultCallback *, _QWORD, HLOCAL, _QWORD))(*(_QWORD *)a4 + 16LL))(
            a4,
            (unsigned int)v23,
            hMem,
            HIDWORD(v22));
    v14 = hMem;
    v12 = v13;
    v20[0] = &RSCA_QUERY_PROVIDER_CONTEXT::`vftable';
    if ( !hMem )
      return v12;
LABEL_13:
    LocalFree(v14);
    return v12;
  }
  v20[0] = &RSCA_QUERY_PROVIDER_CONTEXT::`vftable';
  if ( hMem )
    LocalFree(hMem);
  return 2147500033LL;
}

```

## disassembly

```asm
0x18000aae0  push    rbx
0x18000aae2  push    rbp
0x18000aae3  push    rsi
0x18000aae4  push    rdi
0x18000aae5  push    r12
0x18000aae7  push    r13
0x18000aae9  push    r14
0x18000aaeb  push    r15
0x18000aaed  sub     rsp, 78h
0x18000aaf1  mov     r14, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18000aaf8  lea     rax, ??_7RSCA_QUERY_PROVIDER_CONTEXT@@6B@; const RSCA_QUERY_PROVIDER_CONTEXT::`vftable'
0x18000aaff  xor     r12d, r12d
0x18000ab02  mov     [rsp+0B8h+var_88], rax
0x18000ab07  mov     r13, r9
0x18000ab0a  mov     [rsp+0B8h+var_80], rdx
0x18000ab0f  mov     [rsp+0B8h+var_78], r8
0x18000ab14  lea     rcx, [r14+230h]
0x18000ab1b  mov     [rsp+0B8h+hMem], r12
0x18000ab20  mov     [rsp+0B8h+var_68], r12
0x18000ab25  mov     [rsp+0B8h+var_60], 80004001h
0x18000ab2d  mov     [rsp+0B8h+var_5C], r12d
0x18000ab32  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ab38  mov     ebx, [r14+488h]
0x18000ab3f  lea     rcx, [r14+420h]
0x18000ab46  mov     rsi, rax
0x18000ab49  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ab4f  lea     rcx, [r14+230h]
0x18000ab56  lea     rbx, [rax+rbx*4]
0x18000ab5a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ab60  mov     r15, rax
0x18000ab63  mov     qword ptr [rsp+0B8h+FileTime1.dwLowDateTime], r12
0x18000ab68  cmp     [r14+630h], r12d
0x18000ab6f  jnz     loc_18000AC2F
0x18000ab75  mov     eax, [rbx]
0x18000ab77  cmp     eax, 0FFFFFFFFh
0x18000ab7a  jz      short loc_18000AB9A
0x18000ab7c  mov     rcx, [rsi+rax*8]
0x18000ab80  lea     r8, [rsp+0B8h+var_88]
0x18000ab85  mov     edx, 1000h
0x18000ab8a  call    ?GlobalDoWork@VIRTUAL_MODULE@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; VIRTUAL_MODULE::GlobalDoWork(ulong,IHttpEventProvider *)
0x18000ab8f  cmp     eax, 1
0x18000ab92  jz      short loc_18000AB9A
0x18000ab94  add     rbx, 4
0x18000ab98  jmp     short loc_18000AB75
0x18000ab9a  mov     ebx, [rsp+0B8h+var_60]
0x18000ab9e  test    ebx, ebx
0x18000aba0  js      short loc_18000AC11
0x18000aba2  cmp     [rsp+0B8h+var_5C], r12d
0x18000aba7  jz      short loc_18000ABF0
0x18000aba9  mov     rax, [r13+0]
0x18000abad  mov     edx, ebx
0x18000abaf  mov     r9d, dword ptr [rsp+0B8h+var_68+4]
0x18000abb4  mov     rcx, r13
0x18000abb7  mov     r8, [rsp+0B8h+hMem]
0x18000abbc  mov     rax, [rax+10h]
0x18000abc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abc5  mov     rcx, [rsp+0B8h+hMem]
0x18000abca  mov     ebx, eax
0x18000abcc  lea     rax, ??_7RSCA_QUERY_PROVIDER_CONTEXT@@6B@; const RSCA_QUERY_PROVIDER_CONTEXT::`vftable'
0x18000abd3  mov     [rsp+0B8h+var_88], rax
0x18000abd8  test    rcx, rcx
0x18000abdb  jnz     short loc_18000AC27
0x18000abdd  mov     eax, ebx
0x18000abdf  add     rsp, 78h
0x18000abe3  pop     r15
0x18000abe5  pop     r14
0x18000abe7  pop     r13
0x18000abe9  pop     r12
0x18000abeb  pop     rdi
0x18000abec  pop     rsi
0x18000abed  pop     rbp
0x18000abee  pop     rbx
0x18000abef  retn
0x18000abf0  mov     rcx, [rsp+0B8h+hMem]; hMem
0x18000abf5  lea     rax, ??_7RSCA_QUERY_PROVIDER_CONTEXT@@6B@; const RSCA_QUERY_PROVIDER_CONTEXT::`vftable'
0x18000abfc  mov     [rsp+0B8h+var_88], rax
0x18000ac01  test    rcx, rcx
0x18000ac04  jnz     loc_18000ACE9
0x18000ac0a  mov     eax, 80004001h
0x18000ac0f  jmp     short loc_18000ABDF
0x18000ac11  mov     rcx, [rsp+0B8h+hMem]; hMem
0x18000ac16  lea     rax, ??_7RSCA_QUERY_PROVIDER_CONTEXT@@6B@; const RSCA_QUERY_PROVIDER_CONTEXT::`vftable'
0x18000ac1d  mov     [rsp+0B8h+var_88], rax
0x18000ac22  test    rcx, rcx
0x18000ac25  jz      short loc_18000ABDD
0x18000ac27  call    cs:__imp_LocalFree
0x18000ac2d  jmp     short loc_18000ABDD
0x18000ac2f  lea     rcx, [r14+634h]
0x18000ac36  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000ac3c  cmp     [r14+630h], r12d
0x18000ac43  jz      loc_18000ACD7
0x18000ac49  mov     edi, [r14+49Ch]
0x18000ac50  lea     rcx, [r14+420h]
0x18000ac57  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000ac5d  lea     rdi, [rax+rdi*4]
0x18000ac61  mov     eax, [rdi]
0x18000ac63  cmp     eax, 0FFFFFFFFh
0x18000ac66  jz      short loc_18000AC7F
0x18000ac68  mov     ecx, eax
0x18000ac6a  mov     rcx, [r15+rcx*8]; this
0x18000ac6e  call    ?Resume@VIRTUAL_MODULE@@QEAAXXZ; VIRTUAL_MODULE::Resume(void)
0x18000ac73  mov     eax, [rdi+4]
0x18000ac76  lea     rdi, [rdi+4]
0x18000ac7a  cmp     eax, 0FFFFFFFFh
0x18000ac7d  jnz     short loc_18000AC68
0x18000ac7f  mov     rcx, [r14+5D8h]
0x18000ac86  test    rcx, rcx
0x18000ac89  jz      short loc_18000ACD0
0x18000ac8b  mov     rax, [rcx]
0x18000ac8e  lea     rdx, [rsp+0B8h+FileTime1]
0x18000ac93  mov     rax, [rax+0B0h]
0x18000ac9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac9f  test    eax, eax
0x18000aca1  js      short loc_18000ACD0
0x18000aca3  lea     rdx, [r14+64Ch]; lpFileTime2
0x18000acaa  lea     rcx, [rsp+0B8h+FileTime1]; lpFileTime1
0x18000acaf  call    cs:__imp_CompareFileTime
0x18000acb5  cmp     eax, 1
0x18000acb8  jnz     short loc_18000ACD0
0x18000acba  mov     rax, [r14]
0x18000acbd  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18000acc4  mov     rcx, r14
0x18000acc7  mov     rax, [rax+70h]
0x18000accb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acd0  mov     [r14+630h], r12d
0x18000acd7  lea     rcx, [r14+634h]
0x18000acde  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000ace4  jmp     loc_18000AB75
0x18000ace9  call    cs:__imp_LocalFree
0x18000acef  jmp     loc_18000AC0A
```
