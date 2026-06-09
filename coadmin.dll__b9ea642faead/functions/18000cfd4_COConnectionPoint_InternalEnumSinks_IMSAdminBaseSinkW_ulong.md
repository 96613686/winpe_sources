# COConnectionPoint::InternalEnumSinks(IMSAdminBaseSinkW * * *,ulong *)

- ea: `0x18000cfd4`
- end: `0x18000d178`
- name: `?InternalEnumSinks@COConnectionPoint@@QEAAJPEAPEAPEAUIMSAdminBaseSinkW@@PEAK@Z`
- size: `420`
- prototype: `__int64 __fastcall(COConnectionPoint *__hidden this, struct IMSAdminBaseSinkW ***, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180007c20`

## callees

- `0x1800010b0`
- `0x1800010bc`
- `0x18000cfd4`
- `0x18000d5e0`
- `0x18000fb1e`
- `0x180010010`

## import_xrefs

- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d0ff`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d0ff`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d023`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000d023`

## pseudocode

```c
__int64 __fastcall COConnectionPoint::InternalEnumSinks(
        COConnectionPoint *this,
        struct IMSAdminBaseSinkW ***a2,
        unsigned int *a3)
{
  struct IMSAdminBaseSinkW **v6; // rbx
  unsigned __int64 v7; // rsi
  int v8; // edi
  struct IMSAdminBaseSinkW **v9; // rax
  __int64 v10; // r12
  __int64 v11; // r13
  __int64 v12; // rdx
  __int64 i; // rbp
  struct IMSAdminBaseSinkW *v14; // rcx
  struct IUnknown *v16; // [rsp+78h] [rbp+10h] BYREF
  CReaderWriterLock3 *v17; // [rsp+88h] [rbp+20h]

  v16 = 0;
  if ( a2 && a3 )
  {
    v6 = 0;
    *a2 = 0;
    *a3 = 0;
    v17 = (COConnectionPoint *)((char *)this + 8);
    CReaderWriterLock3::ReadLock((COConnectionPoint *)((char *)this + 8));
    v7 = *((unsigned int *)this + 6);
    if ( *((_QWORD *)this + 6) )
    {
      v8 = 0;
      if ( (_DWORD)v7 )
      {
        v9 = (struct IMSAdminBaseSinkW **)operator new[](saturated_mul(v7, 8u));
        v6 = v9;
        if ( v9 )
        {
          memset_0(v9, 0, 8 * v7);
          v10 = 0;
          v11 = 0;
          if ( *((_DWORD *)this + 7) )
          {
            while ( (unsigned int)v11 < (unsigned int)v7 )
            {
              v12 = *(unsigned int *)(*((_QWORD *)this + 4) + 8 * v10 + 4);
              if ( (_DWORD)v12 )
              {
                v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, struct IUnknown **))(**((_QWORD **)this + 6)
                                                                                            + 40LL))(
                       *((_QWORD *)this + 6),
                       v12,
                       &IID_IMSAdminBaseSink_W,
                       &v16);
                if ( v8 < 0 )
                  goto LABEL_16;
                v8 = SetSinkCallbackSecurityBlanket(v16);
                if ( v8 < 0 )
                  goto LABEL_16;
                v6[v11] = (struct IMSAdminBaseSinkW *)v16;
                v11 = (unsigned int)(v11 + 1);
                v16 = 0;
              }
              v10 = (unsigned int)(v10 + 1);
              if ( (unsigned int)v10 >= *((_DWORD *)this + 7) )
                break;
            }
          }
          *a2 = v6;
          v6 = 0;
          *a3 = v7;
          LODWORD(v7) = 0;
        }
        else
        {
          v8 = -2147024882;
        }
      }
    }
    else
    {
      v8 = -2147467259;
    }
LABEL_16:
    CReaderWriterLock3::ReadUnlock(v17);
    if ( v16 )
    {
      ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
      v16 = 0;
    }
    if ( v6 )
    {
      for ( i = 0; (unsigned int)i < (unsigned int)v7; i = (unsigned int)(i + 1) )
      {
        v14 = v6[i];
        if ( v14 )
        {
          ((void (__fastcall *)(struct IMSAdminBaseSinkW *))v14->lpVtbl->Release)(v14);
          v6[i] = 0;
        }
      }
      operator delete[](v6);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000cfd4  mov     [rsp+arg_0], rbx
0x18000cfd9  push    rbp
0x18000cfda  push    rsi
0x18000cfdb  push    rdi
0x18000cfdc  push    r12
0x18000cfde  push    r13
0x18000cfe0  push    r14
0x18000cfe2  push    r15
0x18000cfe4  sub     rsp, 30h
0x18000cfe8  mov     [rsp+68h+arg_8], 0
0x18000cff1  mov     r14, r8
0x18000cff4  mov     r15, rdx
0x18000cff7  mov     rbp, rcx
0x18000cffa  test    rdx, rdx
0x18000cffd  jz      loc_18000D15C
0x18000d003  test    r8, r8
0x18000d006  jz      loc_18000D15C
0x18000d00c  lea     rax, [rcx+8]
0x18000d010  xor     ebx, ebx
0x18000d012  mov     rcx, rax
0x18000d015  mov     [rdx], rbx
0x18000d018  mov     [r8], ebx
0x18000d01b  mov     [rsp+68h+arg_18], rax
0x18000d023  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000d029  mov     esi, [rbp+18h]
0x18000d02c  cmp     [rbp+30h], rbx
0x18000d030  jnz     short loc_18000D03C
0x18000d032  mov     edi, 80004005h
0x18000d037  jmp     loc_18000D0F7
0x18000d03c  xor     edi, edi
0x18000d03e  test    esi, esi
0x18000d040  jz      loc_18000D0F7
0x18000d046  lea     rcx, [rdi-1]
0x18000d04a  lea     eax, [rdi+8]
0x18000d04d  mul     rsi
0x18000d050  cmovb   rax, rcx
0x18000d054  mov     rcx, rax; unsigned __int64
0x18000d057  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d05c  mov     rbx, rax
0x18000d05f  test    rax, rax
0x18000d062  jnz     short loc_18000D06E
0x18000d064  mov     edi, 8007000Eh
0x18000d069  jmp     loc_18000D0F7
0x18000d06e  lea     r8, ds:0[rsi*8]; Size
0x18000d076  xor     edx, edx; Val
0x18000d078  mov     rcx, rbx; void *
0x18000d07b  call    memset_0
0x18000d080  xor     r12d, r12d
0x18000d083  xor     r13d, r13d
0x18000d086  cmp     [rbp+1Ch], edi
0x18000d089  jbe     short loc_18000D0ED
0x18000d08b  cmp     r13d, esi
0x18000d08e  jnb     short loc_18000D0ED
0x18000d090  mov     rax, [rbp+20h]
0x18000d094  mov     edx, [rax+r12*8+4]
0x18000d099  test    edx, edx
0x18000d09b  jz      short loc_18000D0E4
0x18000d09d  mov     rcx, [rbp+30h]
0x18000d0a1  lea     r9, [rsp+68h+arg_8]
0x18000d0a6  lea     r8, IID_IMSAdminBaseSink_W
0x18000d0ad  mov     rax, [rcx]
0x18000d0b0  mov     rax, [rax+28h]
0x18000d0b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0b9  mov     edi, eax
0x18000d0bb  test    eax, eax
0x18000d0bd  js      short loc_18000D0F7
0x18000d0bf  mov     rcx, [rsp+68h+arg_8]; struct IUnknown *
0x18000d0c4  call    ?SetSinkCallbackSecurityBlanket@@YAJPEAUIUnknown@@@Z; SetSinkCallbackSecurityBlanket(IUnknown *)
0x18000d0c9  mov     edi, eax
0x18000d0cb  test    eax, eax
0x18000d0cd  js      short loc_18000D0F7
0x18000d0cf  mov     rax, [rsp+68h+arg_8]
0x18000d0d4  mov     [rbx+r13*8], rax
0x18000d0d8  inc     r13d
0x18000d0db  mov     [rsp+68h+arg_8], 0
0x18000d0e4  inc     r12d
0x18000d0e7  cmp     r12d, [rbp+1Ch]
0x18000d0eb  jb      short loc_18000D08B
0x18000d0ed  mov     [r15], rbx
0x18000d0f0  xor     ebx, ebx
0x18000d0f2  mov     [r14], esi
0x18000d0f5  xor     esi, esi
0x18000d0f7  mov     rcx, [rsp+68h+arg_18]
0x18000d0ff  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18000d105  mov     rcx, [rsp+68h+arg_8]
0x18000d10a  test    rcx, rcx
0x18000d10d  jz      short loc_18000D124
0x18000d10f  mov     rax, [rcx]
0x18000d112  mov     rax, [rax+10h]
0x18000d116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d11b  mov     [rsp+68h+arg_8], 0
0x18000d124  test    rbx, rbx
0x18000d127  jz      short loc_18000D161
0x18000d129  xor     ebp, ebp
0x18000d12b  test    esi, esi
0x18000d12d  jz      short loc_18000D152
0x18000d12f  mov     rcx, [rbx+rbp*8]
0x18000d133  test    rcx, rcx
0x18000d136  jz      short loc_18000D14C
0x18000d138  mov     rax, [rcx]
0x18000d13b  mov     rax, [rax+10h]
0x18000d13f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d144  mov     qword ptr [rbx+rbp*8], 0
0x18000d14c  inc     ebp
0x18000d14e  cmp     ebp, esi
0x18000d150  jb      short loc_18000D12F
0x18000d152  mov     rcx, rbx; Block
0x18000d155  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000d15a  jmp     short loc_18000D161
0x18000d15c  mov     edi, 80070057h
0x18000d161  mov     rbx, [rsp+68h+arg_0]
0x18000d166  mov     eax, edi
0x18000d168  add     rsp, 30h
0x18000d16c  pop     r15
0x18000d16e  pop     r14
0x18000d170  pop     r13
0x18000d172  pop     r12
0x18000d174  pop     rdi
0x18000d175  pop     rsi
0x18000d176  pop     rbp
0x18000d177  retn
```
