# CFileListener::SaveChange(ulong,ISimpleTableWrite2 *)

- ea: `0x18000e728`
- end: `0x18000e7ce`
- name: `?SaveChange@CFileListener@@AEAAJKPEAUISimpleTableWrite2@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(CFileListener *__hidden this, unsigned int, struct ISimpleTableWrite2 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000d680`

## callees

- `0x18000e728`
- `0x18002056c`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18000e78e`
- `IisRTL!PuDbgPrintW` at `0x18000e78e`

## string_xrefs

- `0x18000e77c`: `[CFileListener::SaveChanges] Unable to track successful changes. AddRowForUpdate failed with hr= 0x%x.\n`

## pseudocode

```c
__int64 __fastcall CFileListener::SaveChange(
        struct ICatalogErrorLogger2 **this,
        __int64 a2,
        struct ISimpleTableWrite2 *a3)
{
  __int64 v3; // rax
  int v5; // eax
  unsigned int v6; // r9d
  unsigned int v7; // ebx
  int v9; // [rsp+28h] [rbp-30h]
  unsigned __int16 *v10; // [rsp+38h] [rbp-20h]
  unsigned __int16 *v11; // [rsp+40h] [rbp-18h]
  unsigned __int16 *v12; // [rsp+48h] [rbp-10h]
  int v13; // [rsp+70h] [rbp+18h] BYREF

  v3 = *(_QWORD *)a3;
  v13 = 0;
  v5 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite2 *, __int64, int *))(v3 + 80))(a3, a2, &v13);
  v7 = v5;
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v9 = v5;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        2621,
        "CFileListener::SaveChange",
        L"[CFileListener::SaveChanges] Unable to track successful changes. AddRowForUpdate failed with hr= 0x%x.\n",
        v9);
    }
    LogEvent(this[70], 0xC002C81A, 1u, v6, v7, 0, 0, v10, v11, v12);
  }
  return v7;
}

```

## disassembly

```asm
0x18000e728  mov     [rsp+arg_0], rbx
0x18000e72d  push    rdi
0x18000e72e  sub     rsp, 50h
0x18000e732  mov     rax, [r8]
0x18000e735  mov     r9, r8
0x18000e738  mov     rdi, rcx
0x18000e73b  mov     [rsp+58h+arg_10], 0
0x18000e743  lea     r8, [rsp+58h+arg_10]
0x18000e748  mov     rcx, r9
0x18000e74b  mov     rax, [rax+50h]
0x18000e74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e754  mov     ebx, eax
0x18000e756  test    eax, eax
0x18000e758  jns     short loc_18000E7C1
0x18000e75a  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e761  jz      short loc_18000E794
0x18000e763  mov     rcx, cs:g_pDebug
0x18000e76a  lea     r9, aCfilelistenerS; "CFileListener::SaveChange"
0x18000e771  mov     dword ptr [rsp+58h+var_30], eax
0x18000e775  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000e77c  lea     rax, aCfilelistenerS_0; "[CFileListener::SaveChanges] Unable to "...
0x18000e783  mov     r8d, 0A3Dh
0x18000e789  mov     qword ptr [rsp+58h+var_38], rax
0x18000e78e  call    cs:__imp_PuDbgPrintW
0x18000e794  mov     rcx, [rdi+230h]; struct ICatalogErrorLogger2 *
0x18000e79b  mov     edx, 0C002C81Ah; unsigned int
0x18000e7a0  mov     [rsp+58h+var_28], 0; unsigned __int16 *
0x18000e7a9  mov     r8d, 1; unsigned int
0x18000e7af  mov     [rsp+58h+var_30], 0; unsigned __int16 *
0x18000e7b8  mov     dword ptr [rsp+58h+var_38], ebx; char
0x18000e7bc  call    ?LogEvent@@YAJPEAUICatalogErrorLogger2@@KKKKPEAG1111@Z; LogEvent(ICatalogErrorLogger2 *,ulong,ulong,ulong,ulong,ushort *,ushort *,ushort *,ushort *,ushort *)
0x18000e7c1  mov     eax, ebx
0x18000e7c3  mov     rbx, [rsp+58h+arg_0]
0x18000e7c8  add     rsp, 50h
0x18000e7cc  pop     rdi
0x18000e7cd  retn
```
