# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18000f7a0`
- end: `0x18000f954`
- name: `??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$01@@U3@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$01@@553@Z`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003dc70`

## callees

- `0x18000f7a0`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f90f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000f90f`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        const GUID *a3,
        const GUID *a4,
        __int64 a5,
        __int64 a6,
        const WCHAR **a7,
        const WCHAR **a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12)
{
  const WCHAR *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rcx
  bool v18; // zf
  int v19; // ecx
  const WCHAR *v20; // rdx
  int v21; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-B1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-99h] BYREF
  unsigned __int8 *v25; // [rsp+60h] [rbp-89h]
  int v26; // [rsp+68h] [rbp-81h]
  int v27; // [rsp+6Ch] [rbp-7Dh]
  __int64 v28; // [rsp+70h] [rbp-79h]
  __int64 v29; // [rsp+78h] [rbp-71h]
  __int64 v30; // [rsp+80h] [rbp-69h]
  __int64 v31; // [rsp+88h] [rbp-61h]
  const WCHAR *v32; // [rsp+90h] [rbp-59h]
  int v33; // [rsp+98h] [rbp-51h]
  int v34; // [rsp+9Ch] [rbp-4Dh]
  const WCHAR *v35; // [rsp+A0h] [rbp-49h]
  int v36; // [rsp+A8h] [rbp-41h]
  int v37; // [rsp+ACh] [rbp-3Dh]
  __int64 v38; // [rsp+B0h] [rbp-39h]
  __int64 v39; // [rsp+B8h] [rbp-31h]
  __int64 v40; // [rsp+C0h] [rbp-29h]
  __int64 v41; // [rsp+C8h] [rbp-21h]
  __int64 v42; // [rsp+D0h] [rbp-19h]
  __int64 v43; // [rsp+D8h] [rbp-11h]
  __int64 v44; // [rsp+E0h] [rbp-9h]
  __int64 v45; // [rsp+E8h] [rbp-1h]

  v44 = a12;
  v42 = a11;
  v40 = a10;
  v38 = a9;
  v45 = 4;
  v43 = 2;
  v41 = 2;
  v15 = *a8;
  v16 = -1;
  v39 = 2;
  if ( v15 )
  {
    v17 = -1;
    do
      v18 = v15[++v17] == 0;
    while ( !v18 );
    v19 = 2 * v17 + 2;
  }
  else
  {
    v15 = &LocaleName;
    v19 = 2;
  }
  v36 = v19;
  v35 = v15;
  v37 = 0;
  v20 = *a7;
  if ( *a7 )
  {
    do
      v18 = v20[++v16] == 0;
    while ( !v18 );
    v21 = 2 * v16 + 2;
  }
  else
  {
    v20 = &LocaleName;
    v21 = 2;
  }
  v33 = v21;
  v30 = a6;
  v28 = a5;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v32 = v20;
  v34 = 0;
  v31 = 4;
  v29 = 4;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v26 = *(unsigned __int16 *)(a2 + 11);
  v25 = a2 + 11;
  UserData.Reserved = 2;
  v27 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, a3, a4, 0xAu, &UserData);
}

```

## disassembly

```asm
0x18000f7a0  mov     [rsp-8+arg_8], rbx
0x18000f7a5  push    rbp
0x18000f7a6  lea     rbp, [rsp-17h]
0x18000f7ab  sub     rsp, 100h
0x18000f7b2  mov     rax, cs:__security_cookie
0x18000f7b9  xor     rax, rsp
0x18000f7bc  mov     [rbp+17h+var_10], rax
0x18000f7c0  mov     rax, [rbp+17h+arg_58]
0x18000f7c4  mov     r11, r8
0x18000f7c7  mov     [rbp+17h+var_20], rax
0x18000f7cb  mov     r8, rdx
0x18000f7ce  mov     rax, [rbp+17h+arg_50]
0x18000f7d2  xor     ebx, ebx
0x18000f7d4  mov     [rbp+17h+var_30], rax
0x18000f7d8  mov     r10, rcx
0x18000f7db  mov     rax, [rbp+17h+arg_48]
0x18000f7df  mov     [rbp+17h+var_40], rax
0x18000f7e3  mov     rax, [rbp+17h+arg_40]
0x18000f7e7  mov     [rbp+17h+var_50], rax
0x18000f7eb  mov     rax, [rbp+17h+arg_38]
0x18000f7ef  mov     [rbp+17h+var_18], 4
0x18000f7f7  mov     [rbp+17h+var_28], 2
0x18000f7ff  mov     [rbp+17h+var_38], 2
0x18000f807  mov     rdx, [rax]
0x18000f80a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000f811  mov     [rbp+17h+var_48], 2
0x18000f819  test    rdx, rdx
0x18000f81c  jz      loc_18000F932
0x18000f822  mov     rcx, rax
0x18000f825  cmp     [rdx+rcx*2+2], bx
0x18000f82a  lea     rcx, [rcx+1]
0x18000f82e  jnz     short loc_18000F825
0x18000f830  lea     ecx, ds:2[rcx*2]
0x18000f837  mov     [rbp+17h+var_58], ecx
0x18000f83a  mov     rcx, [rbp+17h+arg_30]
0x18000f83e  mov     [rbp+17h+var_60], rdx
0x18000f842  mov     [rbp+17h+var_54], ebx
0x18000f845  mov     rdx, [rcx]
0x18000f848  test    rdx, rdx
0x18000f84b  jz      loc_18000F943
0x18000f851  cmp     [rdx+rax*2+2], bx
0x18000f856  lea     rax, [rax+1]
0x18000f85a  jnz     short loc_18000F851
0x18000f85c  lea     eax, ds:2[rax*2]
0x18000f863  mov     [rbp+17h+var_68], eax
0x18000f866  lea     rcx, [r8+0Bh]
0x18000f86a  mov     rax, [rbp+17h+arg_28]
0x18000f86e  mov     [rbp+17h+var_80], rax
0x18000f872  mov     rax, [rbp+17h+arg_20]
0x18000f876  mov     [rbp+17h+var_90], rax
0x18000f87a  movzx   eax, byte ptr [r8]
0x18000f87e  shl     eax, 18h
0x18000f881  mov     dword ptr [rsp+100h+EventDescriptor.Id], eax
0x18000f885  movzx   eax, word ptr [r8+1]
0x18000f88a  mov     dword ptr [rsp+100h+EventDescriptor.Level], eax
0x18000f88e  mov     rax, [r8+3]
0x18000f892  mov     r8, r11; ActivityId
0x18000f895  mov     [rsp+100h+EventDescriptor.Keyword], rax
0x18000f89a  mov     rax, [r10+8]
0x18000f89e  mov     [rsp+100h+var_B0.Ptr], rax
0x18000f8a3  mov     [rbp+17h+var_70], rdx
0x18000f8a7  lea     rdx, [rsp+100h+EventDescriptor]; EventDescriptor
0x18000f8ac  mov     [rbp+17h+var_64], ebx
0x18000f8af  mov     [rbp+17h+var_78], 4
0x18000f8b7  mov     [rbp+17h+var_88], 4
0x18000f8bf  movzx   eax, word ptr [rax]
0x18000f8c2  mov     [rsp+100h+var_B0.Size], eax
0x18000f8c6  movzx   eax, word ptr [rcx]
0x18000f8c9  mov     [rsp+100h+var_98], eax
0x18000f8cd  lea     rax, _TraceLoggingMetadataEnd
0x18000f8d4  mov     [rsp+100h+var_A0], rcx
0x18000f8d9  lea     rcx, _TraceLoggingMetadata
0x18000f8e0  sub     eax, ecx
0x18000f8e2  mov     dword ptr [rsp+100h+var_B0.0Ch], 2
0x18000f8ea  mov     [rbp+17h+var_94], 1
0x18000f8f1  mov     [rsp+100h+var_D0], eax
0x18000f8f5  mov     eax, [rsp+100h+var_D0]
0x18000f8f9  mov     rcx, [r10+20h]; RegHandle
0x18000f8fd  lea     rax, [rsp+100h+var_B0]
0x18000f902  mov     [rsp+100h+UserData], rax; UserData
0x18000f907  mov     [rsp+100h+UserDataCount], 0Ah; UserDataCount
0x18000f90f  call    cs:__imp_EventWriteTransfer
0x18000f915  mov     rcx, [rbp+17h+var_10]
0x18000f919  xor     rcx, rsp; StackCookie
0x18000f91c  call    __security_check_cookie
0x18000f921  mov     rbx, [rsp+100h+arg_8]
0x18000f929  add     rsp, 100h
0x18000f930  pop     rbp
0x18000f931  retn
0x18000f932  lea     rdx, LocaleName
0x18000f939  mov     ecx, 2
0x18000f93e  jmp     loc_18000F837
0x18000f943  lea     rdx, LocaleName
0x18000f94a  mov     eax, 2
0x18000f94f  jmp     loc_18000F863
```
