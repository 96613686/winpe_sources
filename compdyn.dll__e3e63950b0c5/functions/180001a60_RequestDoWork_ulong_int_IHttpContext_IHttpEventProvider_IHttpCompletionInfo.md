# RequestDoWork(ulong,int,IHttpContext *,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180001a60`
- end: `0x180001ea7`
- name: `?RequestDoWork@@YA?AW4REQUEST_NOTIFICATION_STATUS@@KHPEAVIHttpContext@@PEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `1095`
- prototype: `_BOOL8 __fastcall(int, __int64, struct IHttpContext *, __int64, __int64)`
- caller_count: `17`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800019e0`
- `0x180001a00`
- `0x180001a30`
- `0x180005ad0`
- `0x180005b80`
- `0x180005bf0`
- `0x180005c60`
- `0x180005cd0`
- `0x180005d40`
- `0x180005db0`
- `0x180005e20`
- `0x180005e90`
- `0x180005f00`
- `0x180006170`
- `0x180006220`
- `0x180006290`
- `0x180006340`

## callees

- `0x180001010`
- `0x180001a60`
- `0x180001eb0`
- `0x180002820`
- `0x1800035b0`
- `0x180003620`
- `0x180004210`
- `0x180004bc6`
- `0x180008010`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001cc1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001cf1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000532e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000535f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001cc1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180001cf1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000532e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000535f`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001c9c`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180005307`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180001c9c`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180005307`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001e82`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001e94`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001e82`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180001e94`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001e52`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180001e52`

## pseudocode

```c
_BOOL8 __fastcall RequestDoWork(int a1, __int64 a2, struct IHttpContext *a3, __int64 a4, __int64 a5)
{
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // r13
  __int64 v11; // rax
  __int64 v12; // rbp
  struct COMPRESS_META_STORED_CONTEXT *v13; // rbx
  int v14; // edi
  struct COMPRESSION_CONTEXT *v15; // rbp
  __int64 v17; // rax
  __int64 v18; // rbx
  __int64 v19; // rbp
  __int64 v20; // rax
  __int64 v21; // r14
  struct COMPRESS_META_STORED_CONTEXT *v22; // rbx
  const void *v23; // rbx
  size_t v24; // rdi
  void *Ptr; // rax
  struct COMPRESS_META_STORED_CONTEXT *v26; // rax
  int v27; // r9d
  struct COMPRESS_META_STORED_CONTEXT *v28; // r15
  int v29; // ecx
  struct COMPRESS_META_STORED_CONTEXT *v30; // rax
  int v31; // r9d
  __int64 v32; // rax
  __int64 (__fastcall ***v33)(_QWORD, void *); // rax
  struct COMPRESSION_CONTEXT *v34; // r14
  BUFFER *v35; // rcx
  const void *v36; // rbx
  size_t v37; // rdi
  void *v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  struct INativeSectionException *v41; // [rsp+40h] [rbp-48h] BYREF
  __int64 v42; // [rsp+48h] [rbp-40h] BYREF
  struct COMPRESSION_CONTEXT *v43[2]; // [rsp+50h] [rbp-38h] BYREF
  int v44; // [rsp+98h] [rbp+10h] BYREF

  v41 = 0;
  v42 = 0;
  v44 = 0;
  if ( !g_fHttpCompressionInited )
  {
    v14 = 0;
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)g_pCompressionLock);
    if ( g_fHttpCompressionInited || (v14 = HTTP_COMPRESSION::Initialize(v29, &v41), v14 < 0) )
    {
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)g_pCompressionLock);
      if ( v14 < 0 )
        goto LABEL_62;
    }
    else
    {
      g_fHttpCompressionInited = 1;
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)g_pCompressionLock);
    }
  }
  if ( a1 != 256 )
  {
    if ( a1 == 0x20000000 )
    {
      if ( !a5 )
      {
        v8 = *(_QWORD *)a3;
        v43[0] = 0;
        v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v8 + 32))(a3);
        v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a4 + 8LL))(a4) )
        {
          if ( !*(_WORD *)(v10 + 536) && ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a4 + 16LL))(a4) & 2) == 0 )
          {
            v14 = 0;
            goto LABEL_13;
          }
          v11 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 160LL))(a3);
          v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11);
          v13 = (struct COMPRESS_META_STORED_CONTEXT *)(**(__int64 (__fastcall ***)(__int64, void *))v12)(
                                                         v12,
                                                         g_pModuleContext);
          if ( !v13 )
          {
            v30 = (struct COMPRESS_META_STORED_CONTEXT *)operator new(0x60u);
            v13 = v30;
            if ( !v30 )
              goto LABEL_51;
            *((_DWORD *)v30 + 10) = 0;
            *(_QWORD *)v30 = &COMPRESS_META_STORED_CONTEXT::`vftable';
            *((_DWORD *)v30 + 16) = 0;
            *((_QWORD *)v30 + 9) = &MIME_MAP::`vftable';
            *((_QWORD *)v30 + 11) = 0;
            *((_QWORD *)v30 + 4) = (char *)v30 + 24;
            *((_QWORD *)v30 + 3) = (char *)v30 + 24;
            *((_QWORD *)v30 + 7) = (char *)v30 + 48;
            *((_QWORD *)v30 + 6) = (char *)v30 + 48;
            v14 = COMPRESS_META_STORED_CONTEXT::Initialize(v30, a3, &v41, v31);
            if ( v14 < 0 )
            {
              (**(void (__fastcall ***)(struct COMPRESS_META_STORED_CONTEXT *))v13)(v13);
              goto LABEL_13;
            }
            v14 = (*(__int64 (__fastcall **)(__int64, struct COMPRESS_META_STORED_CONTEXT *, void *))(*(_QWORD *)v12 + 8LL))(
                    v12,
                    v13,
                    g_pModuleContext);
            if ( v14 < 0 )
            {
              (**(void (__fastcall ***)(struct COMPRESS_META_STORED_CONTEXT *))v13)(v13);
              v13 = 0;
              if ( v14 == -2147024811 )
              {
                v13 = (struct COMPRESS_META_STORED_CONTEXT *)(**(__int64 (__fastcall ***)(__int64, void *))v12)(
                                                               v12,
                                                               g_pModuleContext);
                v14 = 0;
              }
            }
            if ( v14 < 0 )
            {
LABEL_13:
              if ( v14 >= 0 )
                return v44 != 0;
              goto LABEL_62;
            }
          }
          if ( *((_DWORD *)v13 + 5) )
          {
            v14 = 0;
            goto LABEL_13;
          }
          v14 = HTTP_COMPRESSION::SetupDynamicCompression(a3, v13, v43);
          if ( v14 < 0 )
            goto LABEL_13;
          v15 = v43[0];
        }
        else
        {
          v32 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 240LL))(a3);
          v33 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 56LL))(v32);
          v15 = (struct COMPRESSION_CONTEXT *)(**v33)(v33, g_pModuleContext);
        }
        if ( !v15 )
        {
          v14 = 0;
          goto LABEL_13;
        }
        *((_DWORD *)v15 + 22) = *(unsigned __int16 *)(v10 + 536);
        if ( BUFFER::Resize((struct COMPRESSION_CONTEXT *)((char *)v15 + 40), 32 * *(unsigned __int16 *)(v10 + 536)) )
        {
          v23 = *(const void **)(v10 + 544);
          v24 = 32LL * *(unsigned __int16 *)(v10 + 536);
          Ptr = BUFFER::QueryPtr((struct COMPRESSION_CONTEXT *)((char *)v15 + 40));
          memcpy_0(Ptr, v23, v24);
          *(_WORD *)(v10 + 536) = 0;
          if ( *((_DWORD *)v15 + 22) )
            *((_DWORD *)v15 + 41) = 0;
          *((_DWORD *)v15 + 24) = 0;
          *((_QWORD *)v15 + 13) = BUFFER::QueryPtr((struct COMPRESSION_CONTEXT *)((char *)v15 + 40));
          *((_DWORD *)v15 + 23) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a4 + 16LL))(a4) & 2;
          v14 = HTTP_COMPRESSION::DoDynamicCompression(a3, v15, 1, &v44);
          goto LABEL_13;
        }
LABEL_51:
        v14 = -2147024888;
        goto LABEL_13;
      }
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a5 + 8LL))(a5);
      if ( v14 >= 0 )
      {
        v14 = HTTP_COMPRESSION::DynamicCompressionOnCompletion(a3, &v44);
        goto LABEL_13;
      }
LABEL_62:
      v39 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 80LL))(v39);
      if ( v41 )
        (**(void (__fastcall ***)(struct INativeSectionException *, GUID *, __int64 *))v41)(
          v41,
          &IID_IAppHostConfigException,
          &v42);
      v40 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 32LL))(a3);
      (*(void (__fastcall **)(__int64, __int64, const char *, __int64, int, __int64, _DWORD))(*(_QWORD *)v40 + 24LL))(
        v40,
        500,
        "Internal Server Error",
        19,
        v14,
        v42,
        0);
      if ( v42 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        v42 = 0;
      }
      if ( v41 )
        (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v41 + 16LL))(v41);
      return 0;
    }
    return 0;
  }
  v17 = *(_QWORD *)a3;
  v43[0] = 0;
  v18 = (*(__int64 (__fastcall **)(struct IHttpContext *))(v17 + 32))(a3);
  v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
  if ( (*(unsigned int (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 40LL))(a3)
    || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v18 + 136LL))(v18)
    || !*(_WORD *)(v19 + 536) )
  {
    return 0;
  }
  v20 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a3 + 160LL))(a3);
  v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20);
  v22 = (struct COMPRESS_META_STORED_CONTEXT *)(**(__int64 (__fastcall ***)(__int64, void *))v21)(v21, g_pModuleContext);
  if ( !v22 )
  {
    v26 = (struct COMPRESS_META_STORED_CONTEXT *)operator new(0x60u);
    v28 = v26;
    if ( v26 )
    {
      *((_DWORD *)v26 + 10) = 0;
      *((_QWORD *)v26 + 4) = (char *)v26 + 24;
      *(_QWORD *)v26 = &COMPRESS_META_STORED_CONTEXT::`vftable';
      *((_QWORD *)v26 + 3) = (char *)v26 + 24;
      *((_QWORD *)v26 + 9) = &MIME_MAP::`vftable';
      *((_DWORD *)v26 + 16) = 0;
      *((_QWORD *)v26 + 7) = (char *)v26 + 48;
      *((_QWORD *)v26 + 6) = (char *)v26 + 48;
      *((_QWORD *)v26 + 11) = 0;
      v14 = COMPRESS_META_STORED_CONTEXT::Initialize(v26, a3, &v41, v27);
      if ( v14 >= 0 )
      {
        v22 = v28;
        v14 = (*(__int64 (__fastcall **)(__int64, struct COMPRESS_META_STORED_CONTEXT *, void *))(*(_QWORD *)v21 + 8LL))(
                v21,
                v28,
                g_pModuleContext);
        if ( v14 < 0 )
        {
          v22 = 0;
          (**(void (__fastcall ***)(struct COMPRESS_META_STORED_CONTEXT *))v28)(v28);
          if ( v14 == -2147024811 )
          {
            v22 = (struct COMPRESS_META_STORED_CONTEXT *)(**(__int64 (__fastcall ***)(__int64, void *))v21)(
                                                           v21,
                                                           g_pModuleContext);
            v14 = 0;
          }
        }
        if ( v14 < 0 )
          goto LABEL_62;
        goto LABEL_19;
      }
      (**(void (__fastcall ***)(struct COMPRESS_META_STORED_CONTEXT *))v28)(v28);
    }
    else
    {
      v14 = -2147024888;
    }
LABEL_61:
    if ( v14 < 0 )
      goto LABEL_62;
    return 0;
  }
LABEL_19:
  if ( *((_DWORD *)v22 + 5) )
  {
    v14 = HTTP_COMPRESSION::SetupDynamicCompression(a3, v22, v43);
    if ( v14 < 0 )
      goto LABEL_62;
    v34 = v43[0];
    if ( v43[0] )
    {
      v35 = (struct COMPRESSION_CONTEXT *)((char *)v43[0] + 40);
      *((_DWORD *)v43[0] + 22) = *(unsigned __int16 *)(v19 + 536);
      if ( !BUFFER::Resize(v35, 32 * *(unsigned __int16 *)(v19 + 536)) )
      {
        v14 = -2147024888;
        goto LABEL_62;
      }
      v36 = *(const void **)(v19 + 544);
      v37 = 32LL * *(unsigned __int16 *)(v19 + 536);
      v38 = BUFFER::QueryPtr((struct COMPRESSION_CONTEXT *)((char *)v34 + 40));
      memcpy_0(v38, v36, v37);
      *(_WORD *)(v19 + 536) = 0;
      if ( *((_DWORD *)v34 + 22) )
        *((_DWORD *)v34 + 41) = 0;
      *((_DWORD *)v34 + 24) = 0;
      *((_QWORD *)v34 + 13) = BUFFER::QueryPtr((struct COMPRESSION_CONTEXT *)((char *)v34 + 40));
      *((_DWORD *)v34 + 23) = 0;
      v14 = HTTP_COMPRESSION::DoDynamicCompression(a3, v34, 0, 0);
      goto LABEL_61;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001a60  mov     rax, rsp
0x180001a63  mov     [rax+18h], rbx
0x180001a67  mov     [rax+20h], rbp
0x180001a6b  mov     [rax+10h], edx
0x180001a6e  push    rsi
0x180001a6f  push    rdi
0x180001a70  push    r12
0x180001a72  push    r14
0x180001a74  push    r15
0x180001a76  sub     rsp, 60h
0x180001a7a  xor     r12d, r12d
0x180001a7d  mov     r14, r9
0x180001a80  cmp     cs:?g_fHttpCompressionInited@@3HA, r12d; int g_fHttpCompressionInited
0x180001a87  mov     rsi, r8
0x180001a8a  mov     ebx, ecx
0x180001a8c  mov     [rax-48h], r12
0x180001a90  mov     [rax-40h], r12
0x180001a94  mov     [rax+10h], r12d
0x180001a98  jz      loc_180001E48
0x180001a9e  cmp     ebx, 100h
0x180001aa4  jz      loc_180001BCD
0x180001aaa  cmp     ebx, 20000000h
0x180001ab0  jnz     loc_180001C7B
0x180001ab6  mov     rcx, [rsp+88h+arg_20]
0x180001abe  test    rcx, rcx
0x180001ac1  jnz     loc_180001D30
0x180001ac7  mov     rax, [rsi]
0x180001aca  mov     rcx, rsi
0x180001acd  mov     [rsp+88h+arg_0], r13
0x180001ad5  mov     [rsp+88h+var_38], r12
0x180001ada  mov     rax, [rax+20h]
0x180001ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ae3  mov     rdx, rax
0x180001ae6  mov     rcx, [rax]
0x180001ae9  mov     rax, [rcx+8]
0x180001aed  mov     rcx, rdx
0x180001af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001af5  mov     rcx, [r14]
0x180001af8  mov     r13, rax
0x180001afb  mov     rax, [rcx+8]
0x180001aff  mov     rcx, r14
0x180001b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b07  test    eax, eax
0x180001b09  jz      loc_180005265
0x180001b0f  cmp     [r13+218h], r12w
0x180001b17  jz      loc_180001D5D
0x180001b1d  mov     rax, [rsi]
0x180001b20  mov     rcx, rsi
0x180001b23  mov     rax, [rax+0A0h]
0x180001b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b2f  mov     rdx, rax
0x180001b32  mov     rcx, [rax]
0x180001b35  mov     rax, [rcx+18h]
0x180001b39  mov     rcx, rdx
0x180001b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b41  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x180001b48  mov     rbp, rax
0x180001b4b  mov     rcx, [rax]
0x180001b4e  mov     rax, [rcx]
0x180001b51  mov     rcx, rbp
0x180001b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b59  mov     rbx, rax
0x180001b5c  test    rax, rax
0x180001b5f  jz      loc_180005180
0x180001b65  cmp     [rbx+14h], r12d
0x180001b69  jnz     loc_18000525D
0x180001b6f  lea     r8, [rsp+88h+var_38]; struct COMPRESSION_CONTEXT **
0x180001b74  mov     rdx, rbx; struct COMPRESS_META_STORED_CONTEXT *
0x180001b77  mov     rcx, rsi; struct IHttpContext *
0x180001b7a  call    ?SetupDynamicCompression@HTTP_COMPRESSION@@CAJPEAVIHttpContext@@PEAVCOMPRESS_META_STORED_CONTEXT@@PEAPEAVCOMPRESSION_CONTEXT@@@Z; HTTP_COMPRESSION::SetupDynamicCompression(IHttpContext *,COMPRESS_META_STORED_CONTEXT *,COMPRESSION_CONTEXT * *)
0x180001b7f  mov     edi, eax
0x180001b81  test    eax, eax
0x180001b83  js      short loc_180001B96
0x180001b85  mov     rbp, [rsp+88h+var_38]
0x180001b8a  test    rbp, rbp
0x180001b8d  jnz     loc_180001C82
0x180001b93  mov     edi, r12d
0x180001b96  mov     r13, [rsp+88h+arg_0]
0x180001b9e  test    edi, edi
0x180001ba0  js      loc_18000538F
0x180001ba6  cmp     [rsp+88h+arg_8], 0
0x180001bae  mov     eax, r12d
0x180001bb1  setnz   al
0x180001bb4  lea     r11, [rsp+88h+var_28]
0x180001bb9  mov     rbx, [r11+40h]
0x180001bbd  mov     rbp, [r11+48h]
0x180001bc1  mov     rsp, r11
0x180001bc4  pop     r15
0x180001bc6  pop     r14
0x180001bc8  pop     r12
0x180001bca  pop     rdi
0x180001bcb  pop     rsi
0x180001bcc  retn
0x180001bcd  mov     rax, [rsi]
0x180001bd0  mov     rcx, rsi
0x180001bd3  mov     [rsp+88h+var_38], r12
0x180001bd8  mov     rax, [rax+20h]
0x180001bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001be1  mov     rbx, rax
0x180001be4  mov     rcx, [rax]
0x180001be7  mov     rax, [rcx+8]
0x180001beb  mov     rcx, rbx
0x180001bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bf3  mov     rcx, [rsi]
0x180001bf6  mov     rbp, rax
0x180001bf9  mov     rax, [rcx+28h]
0x180001bfd  mov     rcx, rsi
0x180001c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c05  test    eax, eax
0x180001c07  jnz     short loc_180001C7B
0x180001c09  mov     rcx, [rbx]
0x180001c0c  mov     rax, [rcx+88h]
0x180001c13  mov     rcx, rbx
0x180001c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c1b  test    eax, eax
0x180001c1d  jnz     short loc_180001C7B
0x180001c1f  cmp     [rbp+218h], r12w
0x180001c27  jz      short loc_180001C7B
0x180001c29  mov     rax, [rsi]
0x180001c2c  mov     rcx, rsi
0x180001c2f  mov     rax, [rax+0A0h]
0x180001c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c3b  mov     rdx, rax
0x180001c3e  mov     rcx, [rax]
0x180001c41  mov     rax, [rcx+18h]
0x180001c45  mov     rcx, rdx
0x180001c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c4d  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x180001c54  mov     r14, rax
0x180001c57  mov     rcx, [rax]
0x180001c5a  mov     rax, [rcx]
0x180001c5d  mov     rcx, r14
0x180001c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c65  mov     rbx, rax
0x180001c68  test    rax, rax
0x180001c6b  jz      loc_180001D7C
0x180001c71  cmp     [rbx+14h], r12d
0x180001c75  jnz     loc_1800052C6
0x180001c7b  xor     eax, eax
0x180001c7d  jmp     loc_180001BB4
0x180001c82  movzx   eax, word ptr [r13+218h]
0x180001c8a  lea     rcx, [rbp+28h]
0x180001c8e  mov     [rbp+58h], eax
0x180001c91  movzx   edx, word ptr [r13+218h]
0x180001c99  shl     edx, 5
0x180001c9c  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180001ca2  test    al, al
0x180001ca4  jz      loc_1800052A9
0x180001caa  movzx   edi, word ptr [r13+218h]
0x180001cb2  lea     rcx, [rbp+28h]
0x180001cb6  mov     rbx, [r13+220h]
0x180001cbd  shl     rdi, 5
0x180001cc1  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180001cc7  mov     r8, rdi; Size
0x180001cca  mov     rdx, rbx; Src
0x180001ccd  mov     rcx, rax; void *
0x180001cd0  call    memcpy_0
0x180001cd5  xor     eax, eax
0x180001cd7  mov     [r13+218h], ax
0x180001cdf  cmp     [rbp+58h], eax
0x180001ce2  jbe     short loc_180001CEA
0x180001ce4  mov     [rbp+0A4h], eax
0x180001cea  lea     rcx, [rbp+28h]
0x180001cee  mov     [rbp+60h], eax
0x180001cf1  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180001cf7  mov     [rbp+68h], rax
0x180001cfb  mov     rcx, r14
0x180001cfe  mov     rax, [r14]
0x180001d01  mov     rax, [rax+10h]
0x180001d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d0a  and     eax, 2
0x180001d0d  lea     r9, [rsp+88h+arg_8]; int *
0x180001d15  mov     r8d, 1; int
0x180001d1b  mov     [rbp+5Ch], eax
0x180001d1e  mov     rdx, rbp; struct COMPRESSION_CONTEXT *
0x180001d21  mov     rcx, rsi; struct IHttpContext *
0x180001d24  call    ?DoDynamicCompression@HTTP_COMPRESSION@@CAJPEAVIHttpContext@@PEAVCOMPRESSION_CONTEXT@@HPEAH@Z; HTTP_COMPRESSION::DoDynamicCompression(IHttpContext *,COMPRESSION_CONTEXT *,int,int *)
0x180001d29  mov     edi, eax
0x180001d2b  jmp     loc_180001B96
0x180001d30  mov     rax, [rcx]
0x180001d33  mov     rax, [rax+8]
0x180001d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d3c  mov     edi, eax
0x180001d3e  test    eax, eax
0x180001d40  js      loc_18000538F
0x180001d46  lea     rdx, [rsp+88h+arg_8]; int *
0x180001d4e  mov     rcx, rsi; struct IHttpContext *
0x180001d51  call    ?DynamicCompressionOnCompletion@HTTP_COMPRESSION@@SAJPEAVIHttpContext@@PEAH@Z; HTTP_COMPRESSION::DynamicCompressionOnCompletion(IHttpContext *,int *)
0x180001d56  mov     edi, eax
0x180001d58  jmp     loc_180001B9E
0x180001d5d  mov     rax, [r14]
0x180001d60  mov     rcx, r14
0x180001d63  mov     rax, [rax+10h]
0x180001d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d6c  test    al, 2
0x180001d6e  jnz     loc_180001B1D
0x180001d74  mov     edi, r12d
0x180001d77  jmp     loc_180001B96
0x180001d7c  mov     ecx, 60h ; '`'; Size
0x180001d81  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001d86  mov     r15, rax
0x180001d89  test    rax, rax
0x180001d8c  jz      loc_180005382
0x180001d92  lea     rcx, [r15+18h]
0x180001d96  mov     [r15+28h], r12d
0x180001d9a  lea     rax, ??_7COMPRESS_META_STORED_CONTEXT@@6B@; const COMPRESS_META_STORED_CONTEXT::`vftable'
0x180001da1  mov     [rcx+8], rcx
0x180001da5  mov     [r15], rax
0x180001da8  lea     r8, [rsp+88h+var_48]; struct INativeSectionException **
0x180001dad  lea     rax, ??_7MIME_MAP@@6B@; const MIME_MAP::`vftable'
0x180001db4  mov     [rcx], rcx
0x180001db7  mov     [r15+48h], rax
0x180001dbb  mov     rdx, rsi; struct IHttpContext *
0x180001dbe  lea     rax, [r15+30h]
0x180001dc2  mov     [r15+40h], r12d
0x180001dc6  mov     rcx, r15; this
0x180001dc9  mov     [rax+8], rax
0x180001dcd  mov     [rax], rax
0x180001dd0  mov     [r15+58h], r12
0x180001dd4  call    ?Initialize@COMPRESS_META_STORED_CONTEXT@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@H@Z; COMPRESS_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *,int)
0x180001dd9  mov     edi, eax
0x180001ddb  test    eax, eax
0x180001ddd  js      loc_1800052B3
0x180001de3  mov     rax, [r14]
0x180001de6  mov     rdx, r15
0x180001de9  mov     r8, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x180001df0  mov     rcx, r14
0x180001df3  mov     rbx, r15
0x180001df6  mov     rax, [rax+8]
0x180001dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001dff  mov     edi, eax
0x180001e01  test    eax, eax
0x180001e03  js      short loc_180001E12
0x180001e05  test    edi, edi
0x180001e07  jns     loc_180001C71
0x180001e0d  jmp     loc_18000538F
0x180001e12  mov     rax, [r15]
0x180001e15  mov     rcx, r15
0x180001e18  mov     rbx, r12
0x180001e1b  mov     rax, [rax]
0x180001e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e23  cmp     edi, 80070055h
0x180001e29  jnz     short loc_180001E05
0x180001e2b  mov     rax, [r14]
0x180001e2e  mov     rcx, r14
0x180001e31  mov     rdx, cs:?g_pModuleContext@@3PEAXEA; void * g_pModuleContext
0x180001e38  mov     rax, [rax]
0x180001e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e40  mov     rbx, rax
0x180001e43  mov     edi, r12d
0x180001e46  jmp     short loc_180001E05
0x180001e48  mov     rcx, cs:?g_pCompressionLock@@3PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * g_pCompressionLock
0x180001e4f  mov     edi, r12d
0x180001e52  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180001e58  cmp     cs:?g_fHttpCompressionInited@@3HA, r12d; int g_fHttpCompressionInited
0x180001e5f  jnz     short loc_180001E8D
0x180001e61  lea     rdx, [rsp+88h+var_48]; struct INativeSectionException **
0x180001e66  call    ?Initialize@HTTP_COMPRESSION@@SAJHPEAPEAVINativeSectionException@@@Z; HTTP_COMPRESSION::Initialize(int,INativeSectionException * *)
0x180001e6b  mov     edi, eax
0x180001e6d  test    eax, eax
0x180001e6f  js      short loc_180001E8D
0x180001e71  mov     rcx, cs:?g_pCompressionLock@@3PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * g_pCompressionLock
0x180001e78  mov     cs:?g_fHttpCompressionInited@@3HA, 1; int g_fHttpCompressionInited
0x180001e82  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180001e88  jmp     loc_180001A9E
0x180001e8d  mov     rcx, cs:?g_pCompressionLock@@3PEAVCReaderWriterLock3@@EA; CReaderWriterLock3 * g_pCompressionLock
0x180001e94  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180001e9a  test    edi, edi
0x180001e9c  jns     loc_180001A9E
0x180001ea2  jmp     loc_18000538F
0x180005180  mov     ecx, 60h ; '`'; Size
0x180005185  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000518a  mov     rbx, rax
0x18000518d  test    rax, rax
0x180005190  jz      loc_1800052A9
0x180005196  lea     rax, ??_7COMPRESS_META_STORED_CONTEXT@@6B@; const COMPRESS_META_STORED_CONTEXT::`vftable'
0x18000519d  mov     [rbx+28h], r12d
0x1800051a1  mov     [rbx], rax
0x1800051a4  lea     r8, [rsp+88h+var_48]; struct INativeSectionException **
0x1800051a9  lea     rax, ??_7MIME_MAP@@6B@; const MIME_MAP::`vftable'
0x1800051b0  mov     [rbx+40h], r12d
0x1800051b4  mov     [rbx+48h], rax
0x1800051b8  mov     rdx, rsi; struct IHttpContext *
0x1800051bb  lea     rax, [rbx+18h]
0x1800051bf  mov     [rbx+58h], r12
0x1800051c3  mov     [rax+8], rax
0x1800051c7  mov     rcx, rbx; this
0x1800051ca  mov     [rax], rax
0x1800051cd  lea     rax, [rbx+30h]
0x1800051d1  mov     [rax+8], rax
0x1800051d5  mov     [rax], rax
0x1800051d8  call    ?Initialize@COMPRESS_META_STORED_CONTEXT@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@H@Z; COMPRESS_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *,int)
0x1800051dd  mov     edi, eax
0x1800051df  test    eax, eax
0x1800051e1  jns     short loc_1800051F7
0x1800051e3  mov     rax, [rbx]
0x1800051e6  mov     rcx, rbx
0x1800051e9  mov     rax, [rax]
0x1800051ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051f1  nop
  ... truncated ...
```
