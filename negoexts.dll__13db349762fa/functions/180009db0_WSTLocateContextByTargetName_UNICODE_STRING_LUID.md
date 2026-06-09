# WSTLocateContextByTargetName(_UNICODE_STRING *,_LUID *)

- ea: `0x180009db0`
- end: `0x18000a015`
- name: `?WSTLocateContextByTargetName@@YAPEAU_WST_CONTEXT@@PEAU_UNICODE_STRING@@PEAU_LUID@@@Z`
- size: `613`
- prototype: `struct _WST_CONTEXT *__fastcall(struct _UNICODE_STRING *, struct _LUID *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a29c`
- `0x180017b60`

## callees

- `0x180009db0`
- `0x18000ca08`
- `0x18000ec70`
- `0x180015aa8`
- `0x18001ecee`
- `0x18001ed20`

## import_xrefs

- `ntdll!RtlGetElementGenericTable` at `0x180009e30`
- `ntdll!RtlGetElementGenericTable` at `0x180009e30`
- `ntdll!RtlLookupElementGenericTable` at `0x180009ebd`
- `ntdll!RtlLookupElementGenericTable` at `0x180009ebd`
- `ntdll!RtlLeaveCriticalSection` at `0x180009f06`
- `ntdll!RtlLeaveCriticalSection` at `0x180009f06`
- `ntdll!RtlDeleteElementGenericTable` at `0x180009f9b`
- `ntdll!RtlDeleteElementGenericTable` at `0x180009f9b`
- `ntdll!RtlEnterCriticalSection` at `0x180009e10`
- `ntdll!RtlEnterCriticalSection` at `0x180009e10`
- `ntdll!RtlNumberGenericTableElements` at `0x180009fc5`
- `ntdll!RtlNumberGenericTableElements` at `0x180009fc5`

## pseudocode

```c
struct _WST_CONTEXT *__fastcall WSTLocateContextByTargetName(struct _UNICODE_STRING *a1, struct _LUID *a2)
{
  unsigned __int64 v4; // r14
  ULONG v5; // edi
  __int64 *ElementGenericTable; // rax
  __int64 *v7; // rbx
  struct _WST_CONTEXT *v8; // rbx
  __int128 v9; // xmm0
  struct _WST_CONTEXT **v10; // rax
  struct _WST_CONTEXT **v11; // r9
  unsigned __int64 v13; // rax
  __int64 v14; // r15
  struct _WST_CONTEXT *v15; // rax
  _QWORD Buffer[2]; // [rsp+40h] [rbp-1F8h] BYREF
  _QWORD v17[21]; // [rsp+50h] [rbp-1E8h] BYREF
  __int128 v18; // [rsp+F8h] [rbp-140h]
  _BYTE v19[40]; // [rsp+170h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+198h] [rbp-A0h]

  v4 = (((unsigned __int64)MEMORY[0x7FFE0004] << 32) * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
  RtlEnterCriticalSection(&WSTGlobalContextByTargetTableLock);
  v5 = 0;
  do
  {
    ElementGenericTable = (__int64 *)RtlGetElementGenericTable(&WSTGlobalContextByTargetTable, v5);
    v7 = ElementGenericTable;
    if ( !ElementGenericTable )
      break;
    v13 = ElementGenericTable[1];
    if ( v13 >= NegoExtsGlobalWillNever )
    {
      ++v5;
    }
    else
    {
      if ( v13 > v4 )
        break;
      v14 = *v7;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_qDDZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)(*(_QWORD *)(v14 + 24) + 44LL),
          *(_DWORD *)(*(_QWORD *)(v14 + 24) + 40LL),
          v14 + 168);
      if ( !RtlDeleteElementGenericTable(&WSTGlobalContextByTargetTable, v7) )
        break;
      _InterlockedCompareExchange((volatile signed __int32 *)(v14 + 16), 0, 1);
      WSTDereferenceContext((struct _WST_CONTEXT *)v14);
    }
  }
  while ( v5 < RtlNumberGenericTableElements(&WSTGlobalContextByTargetTable) );
  Buffer[1] = 0;
  memset_0(v17, 0, 0x118u);
  v8 = 0;
  memset_0(v19, 0, 0x88u);
  v9 = (__int128)*a1;
  Buffer[0] = v17;
  v17[0] = 0x545854434F545357LL;
  v20 = (__int64)*a2;
  v17[3] = v19;
  v18 = v9;
  v10 = (struct _WST_CONTEXT **)RtlLookupElementGenericTable(&WSTGlobalContextByTargetTable, Buffer);
  v11 = v10;
  if ( v10 )
  {
    v8 = *v10;
    v15 = (struct _WST_CONTEXT *)(((((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                                  * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64)
                                + WSTGlobalClientExpiration);
    if ( v11[1] < v15 )
      v11[1] = v15;
    WSTReferenceContext(v8);
  }
  RtlLeaveCriticalSection(&WSTGlobalContextByTargetTableLock);
  return v8;
}

```

## disassembly

```asm
0x180009db0  mov     r11, rsp
0x180009db3  push    rbx
0x180009db4  push    r12
0x180009db6  sub     rsp, 228h
0x180009dbd  mov     rax, cs:__security_cookie
0x180009dc4  xor     rax, rsp
0x180009dc7  mov     [rsp+238h+var_38], rax
0x180009dcf  mov     r8d, ds:7FFE0004h
0x180009dd7  mov     r12d, 7FFE0320h
0x180009ddd  mov     [r11+8], rbp
0x180009de1  mov     rbp, rcx
0x180009de4  mov     [r11+10h], rsi
0x180009de8  lea     rcx, ?WSTGlobalContextByTargetTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180009def  mov     [r11+18h], rdi
0x180009df3  mov     rsi, rdx
0x180009df6  mov     rax, [r12]
0x180009dfa  shl     rax, 8
0x180009dfe  shl     r8, 20h
0x180009e02  mul     r8
0x180009e05  mov     [r11-18h], r13
0x180009e09  mov     [r11-20h], r14
0x180009e0d  mov     r14, rdx
0x180009e10  call    cs:__imp_RtlEnterCriticalSection
0x180009e16  xor     edi, edi
0x180009e18  mov     [rsp+238h+var_28], r15
0x180009e20  lea     r13, WPP_GLOBAL_Control
0x180009e27  mov     edx, edi; I
0x180009e29  lea     rcx, ?WSTGlobalContextByTargetTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x180009e30  call    cs:__imp_RtlGetElementGenericTable
0x180009e36  mov     rbx, rax
0x180009e39  test    rax, rax
0x180009e3c  jnz     loc_180009F2A
0x180009e42  xor     edx, edx; Val
0x180009e44  mov     [rsp+238h+var_1F0], 0
0x180009e4d  mov     r8d, 118h; Size
0x180009e53  lea     rcx, [rsp+238h+var_1E8]; void *
0x180009e58  call    memset_0
0x180009e5d  xor     edx, edx; Val
0x180009e5f  lea     rcx, [rsp+238h+var_C8]; void *
0x180009e67  mov     r8d, 88h; Size
0x180009e6d  xor     ebx, ebx
0x180009e6f  call    memset_0
0x180009e74  movups  xmm0, xmmword ptr [rbp+0]
0x180009e78  lea     rax, [rsp+238h+var_1E8]
0x180009e7d  mov     [rsp+238h+Buffer], rax
0x180009e82  lea     rdx, [rsp+238h+Buffer]; Buffer
0x180009e87  mov     rax, 545854434F545357h
0x180009e91  lea     rcx, ?WSTGlobalContextByTargetTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x180009e98  mov     [rsp+238h+var_1E8], rax
0x180009e9d  mov     rax, [rsi]
0x180009ea0  mov     [rsp+238h+var_A0], rax
0x180009ea8  lea     rax, [rsp+238h+var_C8]
0x180009eb0  mov     [rsp+238h+var_1D0], rax
0x180009eb5  movups  [rsp+238h+var_140], xmm0
0x180009ebd  call    cs:__imp_RtlLookupElementGenericTable
0x180009ec3  mov     r15, [rsp+238h+var_28]
0x180009ecb  mov     r9, rax
0x180009ece  mov     r14, [rsp+238h+var_20]
0x180009ed6  mov     r13, [rsp+238h+var_18]
0x180009ede  mov     rdi, [rsp+238h+arg_10]
0x180009ee6  mov     rsi, [rsp+238h+arg_8]
0x180009eee  mov     rbp, [rsp+238h+arg_0]
0x180009ef6  test    rax, rax
0x180009ef9  jnz     loc_180009FDC
0x180009eff  lea     rcx, ?WSTGlobalContextByTargetTableLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180009f06  call    cs:__imp_RtlLeaveCriticalSection
0x180009f0c  mov     rax, rbx
0x180009f0f  mov     rcx, [rsp+238h+var_38]
0x180009f17  xor     rcx, rsp; StackCookie
0x180009f1a  call    __security_check_cookie
0x180009f1f  add     rsp, 228h
0x180009f26  pop     r12
0x180009f28  pop     rbx
0x180009f29  retn
0x180009f2a  mov     rax, [rax+8]
0x180009f2e  cmp     rax, cs:?NegoExtsGlobalWillNever@@3_KA; unsigned __int64 NegoExtsGlobalWillNever
0x180009f35  jnb     loc_180009FD8
0x180009f3b  cmp     rax, r14
0x180009f3e  ja      loc_180009E42
0x180009f44  mov     r15, [rbx]
0x180009f47  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f4e  cmp     rcx, r13
0x180009f51  jz      short loc_180009F91
0x180009f53  test    byte ptr [rcx+1Ch], 2
0x180009f57  jz      short loc_180009F91
0x180009f59  mov     r8, [r15+18h]
0x180009f5d  lea     rax, [r15+0A8h]
0x180009f64  mov     rcx, [rcx+10h]; LoggerHandle
0x180009f68  mov     edx, 10h
0x180009f6d  mov     [rsp+238h+var_208], rax; __int64
0x180009f72  mov     r9, r15
0x180009f75  mov     eax, [r8+28h]
0x180009f79  mov     dword ptr [rsp+238h+var_210], eax; char
0x180009f7d  mov     eax, [r8+2Ch]
0x180009f81  lea     r8, WPP_daa775e63f0b32280135cd3ef20378c2_Traceguids
0x180009f88  mov     dword ptr [rsp+238h+var_218], eax; char
0x180009f8c  call    WPP_SF_qDDZ
0x180009f91  mov     rdx, rbx; Buffer
0x180009f94  lea     rcx, ?WSTGlobalContextByTargetTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x180009f9b  call    cs:__imp_RtlDeleteElementGenericTable
0x180009fa1  test    al, al
0x180009fa3  jz      loc_180009E42
0x180009fa9  xor     edx, edx
0x180009fab  mov     eax, 1
0x180009fb0  lock cmpxchg [r15+10h], edx
0x180009fb6  mov     rcx, r15; struct _WST_CONTEXT *
0x180009fb9  call    ?WSTDereferenceContext@@YAXPEAU_WST_CONTEXT@@@Z; WSTDereferenceContext(_WST_CONTEXT *)
0x180009fbe  lea     rcx, ?WSTGlobalContextByTargetTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x180009fc5  call    cs:__imp_RtlNumberGenericTableElements
0x180009fcb  cmp     edi, eax
0x180009fcd  jb      loc_180009E27
0x180009fd3  jmp     loc_180009E42
0x180009fd8  inc     edi
0x180009fda  jmp     short loc_180009FBE
0x180009fdc  mov     rax, [r12]
0x180009fe0  mov     ecx, ds:7FFE0004h
0x180009fe7  mov     rbx, [r9]
0x180009fea  shl     rax, 8
0x180009fee  shl     rcx, 20h
0x180009ff2  mul     rcx
0x180009ff5  mov     eax, cs:?WSTGlobalClientExpiration@@3KA; ulong WSTGlobalClientExpiration
0x180009ffb  add     rax, rdx
0x180009ffe  cmp     [r9+8], rax
0x18000a002  jnb     short loc_18000A008
0x18000a004  mov     [r9+8], rax
0x18000a008  mov     rcx, rbx; struct _WST_CONTEXT *
0x18000a00b  call    ?WSTReferenceContext@@YAXPEAU_WST_CONTEXT@@@Z; WSTReferenceContext(_WST_CONTEXT *)
0x18000a010  jmp     loc_180009EFF
```
