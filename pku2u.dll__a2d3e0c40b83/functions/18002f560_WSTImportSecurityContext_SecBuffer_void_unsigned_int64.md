# WSTImportSecurityContext(_SecBuffer *,void *,unsigned __int64 *)

- ea: `0x18002f560`
- end: `0x18002f605`
- name: `?WSTImportSecurityContext@@YAJPEAU_SecBuffer@@PEAXPEA_K@Z`
- size: `165`
- prototype: `__int64 __fastcall(struct _SecBuffer *, void *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800241d0`

## callees

- `0x180023ce0`
- `0x18002ee60`
- `0x18002f174`
- `0x18002f560`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x18002f5ce`
- `ntdll!RtlAcquireResourceShared` at `0x18002f5ce`
- `ntdll!RtlReleaseResource` at `0x18002f5e7`
- `ntdll!RtlReleaseResource` at `0x18002f5e7`

## pseudocode

```c
__int64 __fastcall WSTImportSecurityContext(struct _SecBuffer *a1, void *a2, struct _WST_USERMODE_CONTEXT **a3)
{
  int v5; // eax
  struct _WST_USERMODE_CONTEXT *v6; // rbx
  unsigned int v7; // edi
  struct _WST_USERMODE_CONTEXT *v9; // [rsp+68h] [rbp+20h] BYREF

  v9 = 0;
  v5 = WSTCreateUserModeContext(0, a1, &v9);
  v6 = v9;
  v7 = v5;
  if ( v5 >= 0 )
  {
    RtlAcquireResourceShared(&Pku2uGlobalUserModeContextResource, 1u);
    *((_QWORD *)v6 + 4) = a2;
    *((_DWORD *)v6 + 20) |= 0x80u;
    *a3 = v6;
    RtlReleaseResource(&Pku2uGlobalUserModeContextResource);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_bc00a4b8d22a3ddfb8fe7a1a297c3d2e_Traceguids, (unsigned int)v5);
  }
  if ( v6 )
    WSTDereferenceUserModeContext(v6);
  return v7;
}

```

## disassembly

```asm
0x18002f560  push    rbx
0x18002f562  push    rbp
0x18002f563  push    rsi
0x18002f564  push    rdi
0x18002f565  sub     rsp, 28h
0x18002f569  mov     rbp, rdx
0x18002f56c  mov     [rsp+48h+arg_18], 0
0x18002f575  mov     rdx, rcx; struct _SecBuffer *
0x18002f578  mov     rsi, r8
0x18002f57b  xor     ecx, ecx; unsigned __int64
0x18002f57d  lea     r8, [rsp+48h+arg_18]; struct _WST_USERMODE_CONTEXT **
0x18002f582  call    ?WSTCreateUserModeContext@@YAJ_KPEAU_SecBuffer@@PEAPEAU_WST_USERMODE_CONTEXT@@@Z; WSTCreateUserModeContext(unsigned __int64,_SecBuffer *,_WST_USERMODE_CONTEXT * *)
0x18002f587  mov     rbx, [rsp+48h+arg_18]
0x18002f58c  mov     edi, eax
0x18002f58e  test    eax, eax
0x18002f590  jns     short loc_18002F5C5
0x18002f592  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f599  lea     rax, WPP_GLOBAL_Control
0x18002f5a0  cmp     rcx, rax
0x18002f5a3  jz      short loc_18002F5ED
0x18002f5a5  test    byte ptr [rcx+1Ch], 1
0x18002f5a9  jz      short loc_18002F5ED
0x18002f5ab  mov     rcx, [rcx+10h]
0x18002f5af  lea     r8, WPP_bc00a4b8d22a3ddfb8fe7a1a297c3d2e_Traceguids
0x18002f5b6  mov     edx, 0Fh
0x18002f5bb  mov     r9d, edi
0x18002f5be  call    WPP_SF_d
0x18002f5c3  jmp     short loc_18002F5ED
0x18002f5c5  mov     dl, 1; Wait
0x18002f5c7  lea     rcx, ?Pku2uGlobalUserModeContextResource@@3U_RTL_RESOURCE@@A; Resource
0x18002f5ce  call    cs:__imp_RtlAcquireResourceShared
0x18002f5d4  mov     [rbx+20h], rbp
0x18002f5d8  lea     rcx, ?Pku2uGlobalUserModeContextResource@@3U_RTL_RESOURCE@@A; Resource
0x18002f5df  bts     dword ptr [rbx+50h], 7
0x18002f5e4  mov     [rsi], rbx
0x18002f5e7  call    cs:__imp_RtlReleaseResource
0x18002f5ed  test    rbx, rbx
0x18002f5f0  jz      short loc_18002F5FA
0x18002f5f2  mov     rcx, rbx; struct _WST_USERMODE_CONTEXT *
0x18002f5f5  call    ?WSTDereferenceUserModeContext@@YAXPEAU_WST_USERMODE_CONTEXT@@@Z; WSTDereferenceUserModeContext(_WST_USERMODE_CONTEXT *)
0x18002f5fa  mov     eax, edi
0x18002f5fc  add     rsp, 28h
0x18002f600  pop     rdi
0x18002f601  pop     rsi
0x18002f602  pop     rbp
0x18002f603  pop     rbx
0x18002f604  retn
```
