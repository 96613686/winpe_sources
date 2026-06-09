# WSTContextByTargetTableDeleteExNoLock(_RTL_GENERIC_TABLE *,_WST_CONTEXT *)

- ea: `0x18001cf58`
- end: `0x18001cfe7`
- name: `?WSTContextByTargetTableDeleteExNoLock@@YAJPEAU_RTL_GENERIC_TABLE@@PEAU_WST_CONTEXT@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(struct _RTL_GENERIC_TABLE *, struct _WST_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001cecc`

## callees

- `0x18000ca08`
- `0x18001cf58`
- `0x18001d4e8`

## import_xrefs

- `ntdll!RtlLookupElementGenericTable` at `0x18001cf7b`
- `ntdll!RtlLookupElementGenericTable` at `0x18001cf7b`
- `ntdll!RtlDeleteElementGenericTable` at `0x18001cf97`
- `ntdll!RtlDeleteElementGenericTable` at `0x18001cf97`

## pseudocode

```c
__int64 __fastcall WSTContextByTargetTableDeleteExNoLock(struct _RTL_GENERIC_TABLE *a1, struct _WST_CONTEXT *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // rbx
  _QWORD Buffer[3]; // [rsp+30h] [rbp-18h] BYREF

  Buffer[0] = a2;
  Buffer[1] = 0;
  if ( RtlLookupElementGenericTable(&WSTGlobalContextByPointerTable, Buffer) )
  {
    v5 = Buffer[0];
    if ( RtlDeleteElementGenericTable(&WSTGlobalContextByPointerTable, Buffer) )
    {
      _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 16), 0, 1);
      WSTDereferenceContext((struct _WST_CONTEXT *)v5);
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, v4, a2);
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x18001cf58  push    rbx
0x18001cf5a  sub     rsp, 40h
0x18001cf5e  mov     rbx, rdx
0x18001cf61  mov     [rsp+48h+Buffer], rdx
0x18001cf66  lea     rdx, [rsp+48h+Buffer]; Buffer
0x18001cf6b  mov     [rsp+48h+var_10], 0
0x18001cf74  lea     rcx, ?WSTGlobalContextByPointerTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18001cf7b  call    cs:__imp_RtlLookupElementGenericTable
0x18001cf81  test    rax, rax
0x18001cf84  jz      short loc_18001CFB7
0x18001cf86  mov     rbx, [rsp+48h+Buffer]
0x18001cf8b  lea     rdx, [rsp+48h+Buffer]; Buffer
0x18001cf90  lea     rcx, ?WSTGlobalContextByPointerTable@@3U_RTL_GENERIC_TABLE@@A; Table
0x18001cf97  call    cs:__imp_RtlDeleteElementGenericTable
0x18001cf9d  test    al, al
0x18001cf9f  jz      short loc_18001CFB3
0x18001cfa1  xor     edx, edx
0x18001cfa3  lea     eax, [rdx+1]
0x18001cfa6  lock cmpxchg [rbx+10h], edx
0x18001cfab  mov     rcx, rbx; struct _WST_CONTEXT *
0x18001cfae  call    ?WSTDereferenceContext@@YAXPEAU_WST_CONTEXT@@@Z; WSTDereferenceContext(_WST_CONTEXT *)
0x18001cfb3  xor     eax, eax
0x18001cfb5  jmp     short loc_18001CFE1
0x18001cfb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfbe  lea     rax, WPP_GLOBAL_Control
0x18001cfc5  cmp     rcx, rax
0x18001cfc8  jz      short loc_18001CFDC
0x18001cfca  test    byte ptr [rcx+1Ch], 1
0x18001cfce  jz      short loc_18001CFDC
0x18001cfd0  mov     rcx, [rcx+10h]
0x18001cfd4  mov     r9, rbx
0x18001cfd7  call    WPP_SF_qq
0x18001cfdc  mov     eax, 0C0000008h
0x18001cfe1  add     rsp, 40h
0x18001cfe5  pop     rbx
0x18001cfe6  retn
```
