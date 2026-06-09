# W3_SERVER::GetWorkerProcessInfo(ushort const *,ushort const *,ICustomActionResultCallback *)

- ea: `0x18000b3e0`
- end: `0x18000b62b`
- name: `?GetWorkerProcessInfo@W3_SERVER@@QEAAJPEBG0PEAVICustomActionResultCallback@@@Z`
- size: `587`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct ICustomActionResultCallback *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180034070`

## callees

- `0x18000b3e0`
- `0x18000b640`
- `0x180015e40`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b53a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b61a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b53a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b61a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000b5d4`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000b5d4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b432`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b44f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b466`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b576`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b432`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b44f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b466`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000b576`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b54f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b54f`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b609`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b609`

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
0x18000b3e0  push    rbx
0x18000b3e2  push    rbp
0x18000b3e3  push    rsi
0x18000b3e4  push    rdi
0x18000b3e5  push    r12
0x18000b3e7  push    r13
0x18000b3e9  push    r14
0x18000b3eb  push    r15
0x18000b3ed  sub     rsp, 78h
0x18000b3f1  mov     r14, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18000b3f8  lea     rax, ??_7RSCA_QUERY_PROVIDER_CONTEXT@@6B@; const RSCA_QUERY_PROVIDER_CONTEXT::`vftable'
0x18000b3ff  xor     r12d, r12d
0x18000b402  mov     [rsp+0B8h+var_88], rax
0x18000b407  mov     r13, r9
0x18000b40a  mov     [rsp+0B8h+var_80], rdx
0x18000b40f  mov     [rsp+0B8h+var_78], r8
0x18000b414  lea     rcx, [r14+230h]
0x18000b41b  mov     [rsp+0B8h+hMem], r12
0x18000b420  mov     [rsp+0B8h+var_68], r12
0x18000b425  mov     [rsp+0B8h+var_60], 80004001h
0x18000b42d  mov     [rsp+0B8h+var_5C], r12d
0x18000b432  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000b439  nop     dword ptr [rax+rax+00h]
0x18000b43e  mov     ebx, [r14+488h]
0x18000b445  lea     rcx, [r14+420h]
0x18000b44c  mov     rsi, rax
0x18000b44f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000b456  nop     dword ptr [rax+rax+00h]
0x18000b45b  lea     rcx, [r14+230h]
0x18000b462  lea     rbx, [rax+rbx*4]
0x18000b466  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000b46d  nop     dword ptr [rax+rax+00h]
0x18000b472  mov     r15, rax
0x18000b475  mov     qword ptr [rsp+0B8h+FileTime1.dwLowDateTime], r12
0x18000b47a  cmp     [r14+630h], r12d
0x18000b481  jnz     loc_18000B548
0x18000b487  mov     eax, [rbx]
0x18000b489  cmp     eax, 0FFFFFFFFh
0x18000b48c  jz      short loc_18000B4AC
0x18000b48e  mov     rcx, [rsi+rax*8]
0x18000b492  lea     r8, [rsp+0B8h+var_88]
0x18000b497  mov     edx, 1000h
0x18000b49c  call    ?GlobalDoWork@VIRTUAL_MODULE@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; VIRTUAL_MODULE::GlobalDoWork(ulong,IHttpEventProvider *)
0x18000b4a1  cmp     eax, 1
0x18000b4a4  jz      short loc_18000B4AC
0x18000b4a6  add     rbx, 4
0x18000b4aa  jmp     short loc_18000B487
0x18000b4ac  mov     ebx, [rsp+0B8h+var_60]
0x18000b4b0  test    ebx, ebx
0x18000b4b2  js      short loc_18000B524
0x18000b4b4  cmp     [rsp+0B8h+var_5C], r12d
0x18000b4b9  jz      short loc_18000B503
0x18000b4bb  mov     rax, [r13+0]
0x18000b4bf  mov     edx, ebx
0x18000b4c1  mov     r9d, dword ptr [rsp+0B8h+var_68+4]
0x18000b4c6  mov     rcx, r13
0x18000b4c9  mov     r8, [rsp+0B8h+hMem]
0x18000b4ce  mov     rax, [rax+10h]
0x18000b4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4d7  mov     rcx, [rsp+0B8h+hMem]
0x18000b4dc  mov     ebx, eax
0x18000b4de  lea     rax, ??_7RSCA_QUERY_PROVIDER_CONTEXT@@6B@; const RSCA_QUERY_PROVIDER_CONTEXT::`vftable'
0x18000b4e5  mov     [rsp+0B8h+var_88], rax
0x18000b4ea  test    rcx, rcx
0x18000b4ed  jnz     short loc_18000B53A
0x18000b4ef  mov     eax, ebx
0x18000b4f1  add     rsp, 78h
0x18000b4f5  pop     r15
0x18000b4f7  pop     r14
0x18000b4f9  pop     r13
0x18000b4fb  pop     r12
0x18000b4fd  pop     rdi
0x18000b4fe  pop     rsi
0x18000b4ff  pop     rbp
0x18000b500  pop     rbx
0x18000b501  retn
0x18000b503  mov     rcx, [rsp+0B8h+hMem]; hMem
0x18000b508  lea     rax, ??_7RSCA_QUERY_PROVIDER_CONTEXT@@6B@; const RSCA_QUERY_PROVIDER_CONTEXT::`vftable'
0x18000b50f  mov     [rsp+0B8h+var_88], rax
0x18000b514  test    rcx, rcx
0x18000b517  jnz     loc_18000B61A
0x18000b51d  mov     eax, 80004001h
0x18000b522  jmp     short loc_18000B4F1
0x18000b524  mov     rcx, [rsp+0B8h+hMem]; hMem
0x18000b529  lea     rax, ??_7RSCA_QUERY_PROVIDER_CONTEXT@@6B@; const RSCA_QUERY_PROVIDER_CONTEXT::`vftable'
0x18000b530  mov     [rsp+0B8h+var_88], rax
0x18000b535  test    rcx, rcx
0x18000b538  jz      short loc_18000B4EF
0x18000b53a  call    cs:__imp_LocalFree
0x18000b541  nop     dword ptr [rax+rax+00h]
0x18000b546  jmp     short loc_18000B4EF
0x18000b548  lea     rcx, [r14+634h]
0x18000b54f  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000b556  nop     dword ptr [rax+rax+00h]
0x18000b55b  cmp     [r14+630h], r12d
0x18000b562  jz      loc_18000B602
0x18000b568  mov     edi, [r14+49Ch]
0x18000b56f  lea     rcx, [r14+420h]
0x18000b576  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000b57d  nop     dword ptr [rax+rax+00h]
0x18000b582  lea     rdi, [rax+rdi*4]
0x18000b586  mov     eax, [rdi]
0x18000b588  cmp     eax, 0FFFFFFFFh
0x18000b58b  jz      short loc_18000B5A4
0x18000b58d  mov     ecx, eax
0x18000b58f  mov     rcx, [r15+rcx*8]; this
0x18000b593  call    ?Resume@VIRTUAL_MODULE@@QEAAXXZ; VIRTUAL_MODULE::Resume(void)
0x18000b598  mov     eax, [rdi+4]
0x18000b59b  lea     rdi, [rdi+4]
0x18000b59f  cmp     eax, 0FFFFFFFFh
0x18000b5a2  jnz     short loc_18000B58D
0x18000b5a4  mov     rcx, [r14+5D8h]
0x18000b5ab  test    rcx, rcx
0x18000b5ae  jz      short loc_18000B5FB
0x18000b5b0  mov     rax, [rcx]
0x18000b5b3  lea     rdx, [rsp+0B8h+FileTime1]
0x18000b5b8  mov     rax, [rax+0B0h]
0x18000b5bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5c4  test    eax, eax
0x18000b5c6  js      short loc_18000B5FB
0x18000b5c8  lea     rdx, [r14+64Ch]; lpFileTime2
0x18000b5cf  lea     rcx, [rsp+0B8h+FileTime1]; lpFileTime1
0x18000b5d4  call    cs:__imp_CompareFileTime
0x18000b5db  nop     dword ptr [rax+rax+00h]
0x18000b5e0  cmp     eax, 1
0x18000b5e3  jnz     short loc_18000B5FB
0x18000b5e5  mov     rax, [r14]
0x18000b5e8  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18000b5ef  mov     rcx, r14
0x18000b5f2  mov     rax, [rax+70h]
0x18000b5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5fb  mov     [r14+630h], r12d
0x18000b602  lea     rcx, [r14+634h]
0x18000b609  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b610  nop     dword ptr [rax+rax+00h]
0x18000b615  jmp     loc_18000B487
0x18000b61a  call    cs:__imp_LocalFree
0x18000b621  nop     dword ptr [rax+rax+00h]
0x18000b626  jmp     loc_18000B51D
```
