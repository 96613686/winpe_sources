# CASFReaderCallback::OnStatus(WMT_STATUS,long,WMT_ATTR_DATATYPE,uchar *,void *)

- ea: `0x18000c2a0`
- end: `0x18000c5d9`
- name: `?OnStatus@CASFReaderCallback@@UEAAJW4WMT_STATUS@@JW4WMT_ATTR_DATATYPE@@PEAEPEAX@Z`
- size: `825`
- prototype: `__int64 __fastcall(CASFReaderCallback *__hidden this, enum WMT_STATUS, int, enum WMT_ATTR_DATATYPE, unsigned __int8 *Src, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1800077a8`
- `0x18000c2a0`
- `0x18000cba8`
- `0x18001f010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000c5c5`
- `KERNEL32!SetEvent` at `0x18000c5c5`
- `KERNEL32!WaitForSingleObject` at `0x18000c462`
- `KERNEL32!WaitForSingleObject` at `0x18000c4a1`
- `KERNEL32!WaitForSingleObject` at `0x18000c462`
- `KERNEL32!WaitForSingleObject` at `0x18000c4a1`
- `ole32!CoTaskMemAlloc` at `0x18000c317`
- `ole32!CoTaskMemAlloc` at `0x18000c528`
- `ole32!CoTaskMemAlloc` at `0x18000c53d`
- `ole32!CoTaskMemAlloc` at `0x18000c317`
- `ole32!CoTaskMemAlloc` at `0x18000c528`
- `ole32!CoTaskMemAlloc` at `0x18000c53d`
- `ole32!CoTaskMemFree` at `0x18000c363`
- `ole32!CoTaskMemFree` at `0x18000c566`
- `ole32!CoTaskMemFree` at `0x18000c363`
- `ole32!CoTaskMemFree` at `0x18000c566`

## pseudocode

```c
__int64 __fastcall CASFReaderCallback::OnStatus(
        CASFReaderCallback *this,
        int a2,
        int a3,
        enum WMT_ATTR_DATATYPE a4,
        unsigned __int8 *Src)
{
  unsigned int v5; // esi
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  _DWORD *v14; // rax
  _QWORD *v15; // r14
  __int64 v16; // rcx
  _QWORD *v17; // r9
  __int64 v18; // r8
  __int64 v19; // rdx
  void *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // edx
  int v25; // edx
  int v26; // edx
  int v27; // edx
  int v28; // edx
  int v29; // edx
  _DWORD *v30; // rax
  _QWORD *v31; // r14
  _DWORD *v32; // rax

  v5 = 0;
  if ( a2 > 11 )
  {
    v24 = a2 - 12;
    if ( !v24 )
    {
      *(_DWORD *)(*((_QWORD *)this + 2) + 440LL) = a3;
      v20 = *(void **)(*((_QWORD *)this + 2) + 424LL);
      goto LABEL_59;
    }
    v25 = v24 - 1;
    if ( !v25 )
      goto LABEL_30;
    v26 = v25 - 10;
    if ( !v26 )
      return (unsigned int)-1072879843;
    v27 = v26 - 1;
    if ( !v27 )
      return (unsigned int)-1072879843;
    v28 = v27 - 1;
    if ( !v28 )
    {
      v16 = *(_QWORD *)(*((_QWORD *)this + 2) + 104LL);
      if ( !v16 )
        return v5;
      v19 = 594;
      v18 = 25;
      goto LABEL_28;
    }
    v29 = v28 - 1;
    if ( !v29 )
      return (unsigned int)-1072879843;
    if ( v29 != 17 )
      return v5;
    if ( Src )
    {
      v30 = CoTaskMemAlloc(0x10u);
      v31 = v30;
      if ( v30 )
      {
        *v30 = a3;
        v32 = CoTaskMemAlloc(4u);
        v31[1] = v32;
        if ( v32 )
        {
          *v32 = *(_DWORD *)Src;
          v16 = *(_QWORD *)(*((_QWORD *)this + 2) + 104LL);
          if ( !v16 )
            return v5;
          v17 = v31;
          goto LABEL_54;
        }
        CoTaskMemFree(v31);
      }
    }
    v16 = *(_QWORD *)(*((_QWORD *)this + 2) + 104LL);
    if ( !v16 )
      return v5;
    v17 = 0;
LABEL_54:
    v19 = 594;
    v18 = 43;
    goto LABEL_29;
  }
  if ( a2 == 11 )
  {
    *(_DWORD *)(*((_QWORD *)this + 2) + 440LL) = a3;
    if ( WaitForSingleObject(*(HANDLE *)(*((_QWORD *)this + 2) + 432LL), 0) )
    {
      v22 = *((_QWORD *)this + 2);
      v23 = *(_QWORD *)(v22 + 352);
      if ( v23 )
        v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 40LL))(
               v23,
               *(_QWORD *)(v22 + 256) + 10000000LL);
    }
LABEL_35:
    v20 = *(void **)(*((_QWORD *)this + 2) + 432LL);
    goto LABEL_59;
  }
  if ( !a2 )
  {
    v21 = *(_QWORD *)(*((_QWORD *)this + 2) + 104LL);
    if ( v21 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v21 + 24LL))(v21, 3, a3);
    if ( !WaitForSingleObject(*(HANDLE *)(*((_QWORD *)this + 2) + 432LL), 0) )
      return v5;
    *(_DWORD *)(*((_QWORD *)this + 2) + 440LL) = a3;
    goto LABEL_35;
  }
  v8 = a2 - 1;
  if ( !v8 )
  {
LABEL_30:
    *(_DWORD *)(*((_QWORD *)this + 2) + 416LL) = a3;
    v20 = *(void **)(*((_QWORD *)this + 2) + 408LL);
LABEL_59:
    SetEvent(v20);
    return v5;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v16 = *(_QWORD *)(*((_QWORD *)this + 2) + 104LL);
    if ( !v16 )
      return v5;
    v19 = 17;
    v18 = 1;
    goto LABEL_28;
  }
  v10 = v9 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( !v11 )
    {
      CASFReader::SendEOS(*((CASFReader **)this + 2));
      return v5;
    }
    v12 = v11 - 3;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        if ( v13 != 1 )
          return v5;
        if ( Src )
        {
          v14 = CoTaskMemAlloc(0x10u);
          v15 = v14;
          if ( v14 )
          {
            *v14 = a3;
            AMGetWideString(Src);
            if ( v15[1] )
            {
              v16 = *(_QWORD *)(*((_QWORD *)this + 2) + 104LL);
              if ( v16 )
              {
                v17 = v15;
                v18 = 9;
                v19 = 594;
LABEL_29:
                (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD *))(*(_QWORD *)v16 + 24LL))(
                  v16,
                  v19,
                  v18,
                  v17);
                return v5;
              }
              return v5;
            }
            CoTaskMemFree(v15);
          }
        }
        v16 = *(_QWORD *)(*((_QWORD *)this + 2) + 104LL);
        if ( !v16 )
          return v5;
        v19 = 594;
        v18 = 9;
      }
      else
      {
        v16 = *(_QWORD *)(*((_QWORD *)this + 2) + 104LL);
        if ( !v16 )
          return v5;
        v19 = 67;
        v18 = 4;
      }
    }
    else
    {
      v16 = *(_QWORD *)(*((_QWORD *)this + 2) + 104LL);
      if ( !v16 )
        return v5;
      v19 = 67;
      v18 = 3;
    }
LABEL_28:
    v17 = 0;
    goto LABEL_29;
  }
  v16 = *(_QWORD *)(*((_QWORD *)this + 2) + 104LL);
  if ( v16 )
  {
    v17 = 0;
    v18 = 0;
    v19 = 17;
    goto LABEL_29;
  }
  return v5;
}

```

## disassembly

```asm
0x18000c2a0  push    rbx
0x18000c2a2  push    rsi
0x18000c2a3  push    rdi
0x18000c2a4  push    r14
0x18000c2a6  push    r15
0x18000c2a8  sub     rsp, 30h
0x18000c2ac  xor     esi, esi
0x18000c2ae  movsxd  rbx, r8d
0x18000c2b1  mov     rdi, rcx
0x18000c2b4  cmp     edx, 0Bh
0x18000c2b7  jg      loc_18000C4D9
0x18000c2bd  jz      loc_18000C48A
0x18000c2c3  test    edx, edx
0x18000c2c5  jz      loc_18000C432
0x18000c2cb  sub     edx, 1
0x18000c2ce  jz      loc_18000C418
0x18000c2d4  sub     edx, 1
0x18000c2d7  jz      loc_18000C3EA
0x18000c2dd  sub     edx, 1
0x18000c2e0  jz      loc_18000C3CD
0x18000c2e6  sub     edx, 1
0x18000c2e9  jz      loc_18000C3BF
0x18000c2ef  sub     edx, 3
0x18000c2f2  jz      loc_18000C3A3
0x18000c2f8  sub     edx, 1
0x18000c2fb  jz      loc_18000C387
0x18000c301  cmp     edx, 1
0x18000c304  jnz     loc_18000C5CB
0x18000c30a  cmp     [rsp+58h+Src], rsi
0x18000c312  jz      short loc_18000C369
0x18000c314  lea     ecx, [rsi+10h]; cb
0x18000c317  call    cs:__imp_CoTaskMemAlloc
0x18000c31d  mov     r14, rax
0x18000c320  test    rax, rax
0x18000c323  jz      short loc_18000C369
0x18000c325  mov     rcx, [rsp+58h+Src]; Src
0x18000c32d  lea     rdx, [rax+8]
0x18000c331  mov     [rax], ebx
0x18000c333  call    AMGetWideString
0x18000c338  cmp     [r14+8], rsi
0x18000c33c  jz      short loc_18000C360
0x18000c33e  mov     rax, [rdi+10h]
0x18000c342  mov     rcx, [rax+68h]
0x18000c346  test    rcx, rcx
0x18000c349  jz      loc_18000C5CB
0x18000c34f  mov     r9, r14
0x18000c352  lea     r8d, [rsi+9]
0x18000c356  mov     edx, 252h
0x18000c35b  jmp     loc_18000C407
0x18000c360  mov     rcx, r14; pv
0x18000c363  call    cs:__imp_CoTaskMemFree
0x18000c369  mov     rax, [rdi+10h]
0x18000c36d  mov     rcx, [rax+68h]
0x18000c371  test    rcx, rcx
0x18000c374  jz      loc_18000C5CB
0x18000c37a  mov     edx, 252h
0x18000c37f  mov     r8d, 9
0x18000c385  jmp     short loc_18000C404
0x18000c387  mov     rax, [rcx+10h]
0x18000c38b  mov     rcx, [rax+68h]
0x18000c38f  test    rcx, rcx
0x18000c392  jz      loc_18000C5CB
0x18000c398  mov     edx, 43h ; 'C'
0x18000c39d  lea     r8d, [rdx-3Fh]
0x18000c3a1  jmp     short loc_18000C404
0x18000c3a3  mov     rax, [rcx+10h]
0x18000c3a7  mov     rcx, [rax+68h]
0x18000c3ab  test    rcx, rcx
0x18000c3ae  jz      loc_18000C5CB
0x18000c3b4  mov     edx, 43h ; 'C'
0x18000c3b9  lea     r8d, [rdx-40h]
0x18000c3bd  jmp     short loc_18000C404
0x18000c3bf  mov     rcx, [rcx+10h]; this
0x18000c3c3  call    ?SendEOS@CASFReader@@AEAAJXZ; CASFReader::SendEOS(void)
0x18000c3c8  jmp     loc_18000C5CB
0x18000c3cd  mov     rax, [rcx+10h]
0x18000c3d1  mov     rcx, [rax+68h]
0x18000c3d5  test    rcx, rcx
0x18000c3d8  jz      loc_18000C5CB
0x18000c3de  xor     r9d, r9d
0x18000c3e1  xor     r8d, r8d
0x18000c3e4  lea     edx, [r9+11h]
0x18000c3e8  jmp     short loc_18000C407
0x18000c3ea  mov     rax, [rcx+10h]
0x18000c3ee  mov     rcx, [rax+68h]
0x18000c3f2  test    rcx, rcx
0x18000c3f5  jz      loc_18000C5CB
0x18000c3fb  mov     edx, 11h
0x18000c400  lea     r8d, [rdx-10h]
0x18000c404  xor     r9d, r9d
0x18000c407  mov     rax, [rcx]
0x18000c40a  mov     rax, [rax+18h]
0x18000c40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c413  jmp     loc_18000C5CB
0x18000c418  mov     rax, [rcx+10h]
0x18000c41c  mov     [rax+1A0h], ebx
0x18000c422  mov     rcx, [rcx+10h]
0x18000c426  mov     rcx, [rcx+198h]
0x18000c42d  jmp     loc_18000C5C5
0x18000c432  mov     rax, [rcx+10h]
0x18000c436  mov     rcx, [rax+68h]
0x18000c43a  test    rcx, rcx
0x18000c43d  jz      short loc_18000C455
0x18000c43f  mov     rax, [rcx]
0x18000c442  xor     r9d, r9d
0x18000c445  mov     r8, rbx
0x18000c448  mov     rax, [rax+18h]
0x18000c44c  lea     edx, [r9+3]
0x18000c450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c455  mov     rcx, [rdi+10h]
0x18000c459  xor     edx, edx; dwMilliseconds
0x18000c45b  mov     rcx, [rcx+1B0h]; hHandle
0x18000c462  call    cs:__imp_WaitForSingleObject
0x18000c468  test    eax, eax
0x18000c46a  jz      loc_18000C5CB
0x18000c470  mov     rax, [rdi+10h]
0x18000c474  mov     [rax+1B8h], ebx
0x18000c47a  mov     rcx, [rdi+10h]
0x18000c47e  mov     rcx, [rcx+1B0h]
0x18000c485  jmp     loc_18000C5C5
0x18000c48a  mov     rax, [rcx+10h]
0x18000c48e  xor     edx, edx; dwMilliseconds
0x18000c490  mov     [rax+1B8h], ebx
0x18000c496  mov     rcx, [rcx+10h]
0x18000c49a  mov     rcx, [rcx+1B0h]; hHandle
0x18000c4a1  call    cs:__imp_WaitForSingleObject
0x18000c4a7  test    eax, eax
0x18000c4a9  jz      short loc_18000C47A
0x18000c4ab  mov     rdx, [rdi+10h]
0x18000c4af  mov     rcx, [rdx+160h]
0x18000c4b6  test    rcx, rcx
0x18000c4b9  jz      short loc_18000C47A
0x18000c4bb  mov     rax, [rcx]
0x18000c4be  mov     rdx, [rdx+100h]
0x18000c4c5  add     rdx, 989680h
0x18000c4cc  mov     rax, [rax+28h]
0x18000c4d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4d5  mov     esi, eax
0x18000c4d7  jmp     short loc_18000C47A
0x18000c4d9  sub     edx, 0Ch
0x18000c4dc  jz      loc_18000C5B0
0x18000c4e2  sub     edx, 1
0x18000c4e5  jz      loc_18000C418
0x18000c4eb  sub     edx, 0Ah
0x18000c4ee  jz      loc_18000C5A9
0x18000c4f4  sub     edx, 1
0x18000c4f7  jz      loc_18000C5A9
0x18000c4fd  sub     edx, 1
0x18000c500  jz      loc_18000C58C
0x18000c506  sub     edx, 1
0x18000c509  jz      loc_18000C5A9
0x18000c50f  cmp     edx, 11h
0x18000c512  jnz     loc_18000C5CB
0x18000c518  mov     r15, [rsp+58h+Src]
0x18000c520  test    r15, r15
0x18000c523  jz      short loc_18000C56C
0x18000c525  lea     ecx, [rdx-1]; cb
0x18000c528  call    cs:__imp_CoTaskMemAlloc
0x18000c52e  mov     r14, rax
0x18000c531  test    rax, rax
0x18000c534  jz      short loc_18000C56C
0x18000c536  mov     ecx, 4; cb
0x18000c53b  mov     [rax], ebx
0x18000c53d  call    cs:__imp_CoTaskMemAlloc
0x18000c543  mov     [r14+8], rax
0x18000c547  test    rax, rax
0x18000c54a  jz      short loc_18000C563
0x18000c54c  mov     ecx, [r15]
0x18000c54f  mov     [rax], ecx
0x18000c551  mov     rax, [rdi+10h]
0x18000c555  mov     rcx, [rax+68h]
0x18000c559  test    rcx, rcx
0x18000c55c  jz      short loc_18000C5CB
0x18000c55e  mov     r9, r14
0x18000c561  jmp     short loc_18000C57C
0x18000c563  mov     rcx, r14; pv
0x18000c566  call    cs:__imp_CoTaskMemFree
0x18000c56c  mov     rax, [rdi+10h]
0x18000c570  mov     rcx, [rax+68h]
0x18000c574  test    rcx, rcx
0x18000c577  jz      short loc_18000C5CB
0x18000c579  xor     r9d, r9d
0x18000c57c  mov     edx, 252h
0x18000c581  mov     r8d, 2Bh ; '+'
0x18000c587  jmp     loc_18000C407
0x18000c58c  mov     rax, [rcx+10h]
0x18000c590  mov     rcx, [rax+68h]
0x18000c594  test    rcx, rcx
0x18000c597  jz      short loc_18000C5CB
0x18000c599  mov     edx, 252h
0x18000c59e  mov     r8d, 19h
0x18000c5a4  jmp     loc_18000C404
0x18000c5a9  mov     esi, 0C00D271Dh
0x18000c5ae  jmp     short loc_18000C5CB
0x18000c5b0  mov     rax, [rcx+10h]
0x18000c5b4  mov     [rax+1B8h], ebx
0x18000c5ba  mov     rcx, [rcx+10h]
0x18000c5be  mov     rcx, [rcx+1A8h]; hEvent
0x18000c5c5  call    cs:__imp_SetEvent
0x18000c5cb  mov     eax, esi
0x18000c5cd  add     rsp, 30h
0x18000c5d1  pop     r15
0x18000c5d3  pop     r14
0x18000c5d5  pop     rdi
0x18000c5d6  pop     rsi
0x18000c5d7  pop     rbx
0x18000c5d8  retn
```
