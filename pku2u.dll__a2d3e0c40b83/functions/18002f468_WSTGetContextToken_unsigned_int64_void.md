# WSTGetContextToken(unsigned __int64,void * *)

- ea: `0x18002f468`
- end: `0x18002f558`
- name: `?WSTGetContextToken@@YAJ_KPEAPEAX@Z`
- size: `240`
- prototype: `__int64 __fastcall(unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180024130`

## callees

- `0x180023cb8`
- `0x180023e70`
- `0x18002f174`
- `0x18002f468`
- `0x18002fbe4`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18002f51a`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002f51a`
- `ntdll!RtlReleaseResource` at `0x18002f52e`
- `ntdll!RtlReleaseResource` at `0x18002f52e`

## pseudocode

```c
__int64 __fastcall WSTGetContextToken(unsigned __int64 a1, void **a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  struct _WST_USERMODE_CONTEXT *v6; // rdi
  struct _WST_USERMODE_CONTEXT *v8; // [rsp+68h] [rbp+10h] BYREF

  v8 = 0;
  if ( a2 )
  {
    v5 = WSTReferenceUserModeContextByLsaHandle(a1, 0, &v8);
    v6 = v8;
    v4 = v5;
    if ( v5 >= 0 )
    {
      RtlAcquireResourceExclusive(&Pku2uGlobalUserModeContextResource, 1u);
      *a2 = (void *)*((_QWORD *)v6 + 4);
      RtlReleaseResource(&Pku2uGlobalUserModeContextResource);
      if ( !*a2 )
        v4 = -2146893045;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_bc00a4b8d22a3ddfb8fe7a1a297c3d2e_Traceguids, a1, v5);
    }
    if ( v6 )
      WSTDereferenceUserModeContext(v6);
  }
  else
  {
    v4 = -1073741811;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_bc00a4b8d22a3ddfb8fe7a1a297c3d2e_Traceguids);
  }
  return v4;
}

```

## disassembly

```asm
0x18002f468  push    rbx
0x18002f46a  push    rbp
0x18002f46b  push    rsi
0x18002f46c  push    rdi
0x18002f46d  sub     rsp, 38h
0x18002f471  mov     [rsp+58h+arg_8], 0
0x18002f47a  mov     rsi, rdx
0x18002f47d  mov     rbp, rcx
0x18002f480  test    rdx, rdx
0x18002f483  jnz     short loc_18002F4C3
0x18002f485  mov     ebx, 0C000000Dh
0x18002f48a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f491  lea     rax, WPP_GLOBAL_Control
0x18002f498  cmp     rcx, rax
0x18002f49b  jz      loc_18002F54D
0x18002f4a1  test    byte ptr [rcx+1Ch], 1
0x18002f4a5  jz      loc_18002F54D
0x18002f4ab  mov     rcx, [rcx+10h]
0x18002f4af  lea     edx, [rsi+10h]
0x18002f4b2  lea     r8, WPP_bc00a4b8d22a3ddfb8fe7a1a297c3d2e_Traceguids
0x18002f4b9  call    WPP_SF_
0x18002f4be  jmp     loc_18002F54D
0x18002f4c3  lea     r8, [rsp+58h+arg_8]; struct _WST_USERMODE_CONTEXT **
0x18002f4c8  xor     edx, edx; unsigned __int8
0x18002f4ca  call    ?WSTReferenceUserModeContextByLsaHandle@@YAJ_KEPEAPEAU_WST_USERMODE_CONTEXT@@@Z; WSTReferenceUserModeContextByLsaHandle(unsigned __int64,uchar,_WST_USERMODE_CONTEXT * *)
0x18002f4cf  mov     rdi, [rsp+58h+arg_8]
0x18002f4d4  mov     ebx, eax
0x18002f4d6  test    eax, eax
0x18002f4d8  jns     short loc_18002F511
0x18002f4da  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f4e1  lea     rax, WPP_GLOBAL_Control
0x18002f4e8  cmp     rcx, rax
0x18002f4eb  jz      short loc_18002F540
0x18002f4ed  test    byte ptr [rcx+1Ch], 1
0x18002f4f1  jz      short loc_18002F540
0x18002f4f3  mov     rcx, [rcx+10h]
0x18002f4f7  lea     r8, WPP_bc00a4b8d22a3ddfb8fe7a1a297c3d2e_Traceguids
0x18002f4fe  mov     edx, 11h
0x18002f503  mov     [rsp+58h+var_38], ebx
0x18002f507  mov     r9, rbp
0x18002f50a  call    WPP_SF_qD
0x18002f50f  jmp     short loc_18002F540
0x18002f511  mov     dl, 1; Wait
0x18002f513  lea     rcx, ?Pku2uGlobalUserModeContextResource@@3U_RTL_RESOURCE@@A; Resource
0x18002f51a  call    cs:__imp_RtlAcquireResourceExclusive
0x18002f520  mov     rax, [rdi+20h]
0x18002f524  lea     rcx, ?Pku2uGlobalUserModeContextResource@@3U_RTL_RESOURCE@@A; Resource
0x18002f52b  mov     [rsi], rax
0x18002f52e  call    cs:__imp_RtlReleaseResource
0x18002f534  cmp     qword ptr [rsi], 0
0x18002f538  mov     eax, 8009030Bh
0x18002f53d  cmovz   ebx, eax
0x18002f540  test    rdi, rdi
0x18002f543  jz      short loc_18002F54D
0x18002f545  mov     rcx, rdi; struct _WST_USERMODE_CONTEXT *
0x18002f548  call    ?WSTDereferenceUserModeContext@@YAXPEAU_WST_USERMODE_CONTEXT@@@Z; WSTDereferenceUserModeContext(_WST_USERMODE_CONTEXT *)
0x18002f54d  mov     eax, ebx
0x18002f54f  add     rsp, 38h
0x18002f553  pop     rdi
0x18002f554  pop     rsi
0x18002f555  pop     rbp
0x18002f556  pop     rbx
0x18002f557  retn
```
