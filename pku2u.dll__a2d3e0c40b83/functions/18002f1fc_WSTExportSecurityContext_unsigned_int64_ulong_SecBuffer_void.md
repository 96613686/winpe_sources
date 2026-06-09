# WSTExportSecurityContext(unsigned __int64,ulong,_SecBuffer *,void * *)

- ea: `0x18002f1fc`
- end: `0x18002f37e`
- name: `?WSTExportSecurityContext@@YAJ_KKPEAU_SecBuffer@@PEAPEAX@Z`
- size: `386`
- prototype: `int(unsigned __int64, unsigned int, struct _SecBuffer *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024090`

## callees

- `0x1800057f0`
- `0x180023e70`
- `0x18002f174`
- `0x18002f1fc`
- `0x18002f740`
- `0x18002f878`
- `0x18002fbe4`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x18002f2fd`
- `ntdll!RtlAcquireResourceShared` at `0x18002f2fd`
- `ntdll!NtDuplicateObject` at `0x18002f340`
- `ntdll!NtDuplicateObject` at `0x18002f340`
- `ntdll!RtlReleaseResource` at `0x18002f34f`
- `ntdll!RtlReleaseResource` at `0x18002f34f`

## pseudocode

```c
__int64 __fastcall WSTExportSecurityContext(unsigned __int64 a1, char a2, struct _SecBuffer *a3, void **a4)
{
  int v9; // eax
  struct _WST_USERMODE_CONTEXT *v10; // rbx
  NTSTATUS v11; // edi
  int v12; // eax
  struct _WST_CONTEXT_DATA *v13; // rbp
  struct _WST_USERMODE_CONTEXT *v14; // [rsp+40h] [rbp-48h] BYREF
  struct _WST_CONTEXT_DATA *v15; // [rsp+48h] [rbp-40h] BYREF
  unsigned int v16; // [rsp+98h] [rbp+10h] BYREF

  v14 = 0;
  v15 = 0;
  v16 = 0;
  if ( (a2 & 1) != 0 )
    return 2148074242LL;
  if ( a4 )
    *a4 = 0;
  a3->pvBuffer = 0;
  *(_QWORD *)&a3->cbBuffer = 0;
  v9 = WSTReferenceUserModeContextByLsaHandle(a1, 0, &v14);
  v10 = v14;
  v11 = v9;
  if ( v9 >= 0 )
  {
    v12 = WSTMapContextToContextData(v14, (unsigned __int8 **)&v15, &v16);
    v13 = v15;
    v11 = v12;
    if ( v12 >= 0 )
    {
      v11 = WSTPackContextFromContextData(v15, a3);
      if ( v11 >= 0 )
      {
        *((_DWORD *)a3->pvBuffer + 10) |= 0x100u;
        if ( a4 )
        {
          RtlAcquireResourceShared(&Pku2uGlobalUserModeContextResource, 1u);
          if ( (a2 & 2) != 0 )
          {
            *a4 = (void *)*((_QWORD *)v10 + 4);
            *((_QWORD *)v10 + 4) = 0;
          }
          else
          {
            v11 = NtDuplicateObject((HANDLE)0xFFFFFFFFFFFFFFFFLL, *((HANDLE *)v10 + 4), 0, a4, 0, 0, 2u);
          }
          RtlReleaseResource(&Pku2uGlobalUserModeContextResource);
        }
      }
    }
    if ( v13 )
      Pku2uFree(v13);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_bc00a4b8d22a3ddfb8fe7a1a297c3d2e_Traceguids, a1, v9);
  }
  if ( v10 )
    WSTDereferenceUserModeContext(v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002f1fc  mov     rax, rsp
0x18002f1ff  push    rbx
0x18002f200  push    rbp
0x18002f201  push    rsi
0x18002f202  push    rdi
0x18002f203  push    r14
0x18002f205  push    r15
0x18002f207  sub     rsp, 58h
0x18002f20b  mov     qword ptr [rax-48h], 0
0x18002f213  mov     rsi, r9
0x18002f216  mov     qword ptr [rax-40h], 0
0x18002f21e  mov     r14, r8
0x18002f221  mov     dword ptr [rax+10h], 0
0x18002f228  mov     r15d, edx
0x18002f22b  mov     rbp, rcx
0x18002f22e  test    dl, 1
0x18002f231  jz      short loc_18002F23D
0x18002f233  mov     eax, 80090302h
0x18002f238  jmp     loc_18002F371
0x18002f23d  test    rsi, rsi
0x18002f240  jz      short loc_18002F249
0x18002f242  mov     qword ptr [r9], 0
0x18002f249  mov     qword ptr [r8+8], 0
0x18002f251  xor     edx, edx; unsigned __int8
0x18002f253  mov     qword ptr [r8], 0
0x18002f25a  lea     r8, [rsp+88h+var_48]; struct _WST_USERMODE_CONTEXT **
0x18002f25f  call    ?WSTReferenceUserModeContextByLsaHandle@@YAJ_KEPEAPEAU_WST_USERMODE_CONTEXT@@@Z; WSTReferenceUserModeContextByLsaHandle(unsigned __int64,uchar,_WST_USERMODE_CONTEXT * *)
0x18002f264  mov     rbx, [rsp+88h+var_48]
0x18002f269  mov     edi, eax
0x18002f26b  test    eax, eax
0x18002f26d  jns     short loc_18002F2B1
0x18002f26f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f276  lea     rax, WPP_GLOBAL_Control
0x18002f27d  cmp     rcx, rax
0x18002f280  jz      loc_18002F362
0x18002f286  test    byte ptr [rcx+1Ch], 1
0x18002f28a  jz      loc_18002F362
0x18002f290  mov     rcx, [rcx+10h]
0x18002f294  lea     r8, WPP_bc00a4b8d22a3ddfb8fe7a1a297c3d2e_Traceguids
0x18002f29b  mov     edx, 0Eh
0x18002f2a0  mov     [rsp+88h+DesiredAccess], edi
0x18002f2a4  mov     r9, rbp
0x18002f2a7  call    WPP_SF_qD
0x18002f2ac  jmp     loc_18002F362
0x18002f2b1  lea     r8, [rsp+88h+arg_8]; unsigned int *
0x18002f2b9  mov     rcx, rbx; struct _WST_USERMODE_CONTEXT *
0x18002f2bc  lea     rdx, [rsp+88h+var_40]; unsigned __int8 **
0x18002f2c1  call    ?WSTMapContextToContextData@@YAJPEAU_WST_USERMODE_CONTEXT@@PEAPEAEPEAK@Z; WSTMapContextToContextData(_WST_USERMODE_CONTEXT *,uchar * *,ulong *)
0x18002f2c6  mov     rbp, [rsp+88h+var_40]
0x18002f2cb  mov     edi, eax
0x18002f2cd  test    eax, eax
0x18002f2cf  js      loc_18002F355
0x18002f2d5  mov     rdx, r14; struct _SecBuffer *
0x18002f2d8  mov     rcx, rbp; struct _WST_CONTEXT_DATA *
0x18002f2db  call    ?WSTPackContextFromContextData@@YAJPEAU_WST_CONTEXT_DATA@@PEAU_SecBuffer@@@Z; WSTPackContextFromContextData(_WST_CONTEXT_DATA *,_SecBuffer *)
0x18002f2e0  mov     edi, eax
0x18002f2e2  test    eax, eax
0x18002f2e4  js      short loc_18002F355
0x18002f2e6  mov     rax, [r14+8]
0x18002f2ea  bts     dword ptr [rax+28h], 8
0x18002f2ef  test    rsi, rsi
0x18002f2f2  jz      short loc_18002F355
0x18002f2f4  mov     dl, 1; Wait
0x18002f2f6  lea     rcx, ?Pku2uGlobalUserModeContextResource@@3U_RTL_RESOURCE@@A; Resource
0x18002f2fd  call    cs:__imp_RtlAcquireResourceShared
0x18002f303  test    r15b, 2
0x18002f307  jz      short loc_18002F31A
0x18002f309  mov     rax, [rbx+20h]
0x18002f30d  mov     [rsi], rax
0x18002f310  mov     qword ptr [rbx+20h], 0
0x18002f318  jmp     short loc_18002F348
0x18002f31a  mov     rdx, [rbx+20h]; SourceHandle
0x18002f31e  mov     r9, rsi; TargetHandle
0x18002f321  mov     [rsp+88h+Options], 2; Options
0x18002f329  xor     r8d, r8d; TargetProcessHandle
0x18002f32c  mov     [rsp+88h+HandleAttributes], 0; HandleAttributes
0x18002f334  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x18002f338  mov     [rsp+88h+DesiredAccess], 0; DesiredAccess
0x18002f340  call    cs:__imp_NtDuplicateObject
0x18002f346  mov     edi, eax
0x18002f348  lea     rcx, ?Pku2uGlobalUserModeContextResource@@3U_RTL_RESOURCE@@A; Resource
0x18002f34f  call    cs:__imp_RtlReleaseResource
0x18002f355  test    rbp, rbp
0x18002f358  jz      short loc_18002F362
0x18002f35a  mov     rcx, rbp; void *
0x18002f35d  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18002f362  test    rbx, rbx
0x18002f365  jz      short loc_18002F36F
0x18002f367  mov     rcx, rbx; struct _WST_USERMODE_CONTEXT *
0x18002f36a  call    ?WSTDereferenceUserModeContext@@YAXPEAU_WST_USERMODE_CONTEXT@@@Z; WSTDereferenceUserModeContext(_WST_USERMODE_CONTEXT *)
0x18002f36f  mov     eax, edi
0x18002f371  add     rsp, 58h
0x18002f375  pop     r15
0x18002f377  pop     r14
0x18002f379  pop     rdi
0x18002f37a  pop     rsi
0x18002f37b  pop     rbp
0x18002f37c  pop     rbx
0x18002f37d  retn
```
