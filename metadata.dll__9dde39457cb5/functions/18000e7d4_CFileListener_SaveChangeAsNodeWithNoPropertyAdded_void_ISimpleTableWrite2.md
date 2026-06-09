# CFileListener::SaveChangeAsNodeWithNoPropertyAdded(void * *,ISimpleTableWrite2 *)

- ea: `0x18000e7d4`
- end: `0x18000e9b0`
- name: `?SaveChangeAsNodeWithNoPropertyAdded@CFileListener@@AEAAJPEAPEAXPEAUISimpleTableWrite2@@@Z`
- size: `476`
- prototype: `__int64 __fastcall(CFileListener *__hidden this, void **, struct ISimpleTableWrite2 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000d680`

## callees

- `0x18000e7d4`
- `0x18002056c`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18000e957`
- `IisRTL!PuDbgPrintW` at `0x18000e957`

## string_xrefs

- `0x18000e939`: `[CFileListener::SaveChanges] Unable to track successful changes. AddRowForUpdate failed with hr= 0x%x.\n`

## pseudocode

```c
__int64 __fastcall CFileListener::SaveChangeAsNodeWithNoPropertyAdded(
        struct ICatalogErrorLogger2 **this,
        void **a2,
        struct ISimpleTableWrite2 *a3)
{
  __int64 v3; // rax
  int v7; // ebx
  unsigned int v8; // r9d
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 (__fastcall *v11)(struct ISimpleTableWrite2 *, _QWORD, __int64, _DWORD *, _BYTE *, _QWORD *); // rax
  unsigned __int16 *v13; // [rsp+28h] [rbp-91h]
  unsigned __int16 *v14; // [rsp+38h] [rbp-81h]
  unsigned __int16 *v15; // [rsp+40h] [rbp-79h]
  unsigned __int16 *v16; // [rsp+48h] [rbp-71h]
  unsigned int v17; // [rsp+50h] [rbp-69h] BYREF
  _DWORD v18[10]; // [rsp+58h] [rbp-61h] BYREF
  _QWORD v19[10]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v20[12]; // [rsp+D0h] [rbp+17h] BYREF
  int v21; // [rsp+DCh] [rbp+23h]

  v3 = *(_QWORD *)a3;
  v17 = 0;
  v7 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite2 *, unsigned int *))(v3 + 72))(a3, &v17);
  if ( v7 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v9 = 2666;
LABEL_7:
      LODWORD(v13) = v7;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\listener.cpp",
        v9,
        "CFileListener::SaveChangeAsNodeWithNoPropertyAdded",
        L"[CFileListener::SaveChanges] Unable to track successful changes. AddRowForUpdate failed with hr= 0x%x.\n",
        v13);
      goto LABEL_8;
    }
    goto LABEL_8;
  }
  v19[0] = L"#LocationWithNoProperties";
  v19[1] = &dword_18004809C;
  v19[2] = &qword_180048748;
  v19[4] = a2[4];
  v18[0] = 0;
  v19[5] = byte_180048098;
  v19[6] = &dword_180048094;
  v19[7] = a2[7];
  v19[8] = byte_180048090;
  v19[9] = &dword_180048744;
  v10 = *(_QWORD *)a3;
  v18[1] = 1;
  v18[2] = 2;
  v18[3] = 3;
  v11 = *(__int64 (__fastcall **)(struct ISimpleTableWrite2 *, _QWORD, __int64, _DWORD *, _BYTE *, _QWORD *))(v10 + 88);
  v18[4] = 4;
  v18[5] = 5;
  v18[6] = 6;
  v18[7] = 7;
  v18[8] = 8;
  v18[9] = 9;
  v21 = 0;
  v19[3] = 0;
  v7 = v11(a3, v17, 10, v18, v20, v19);
  if ( v7 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v9 = 2723;
      goto LABEL_7;
    }
LABEL_8:
    LogEvent(this[70], 0xC002C81A, 1u, v8, v7, 0, 0, v14, v15, v16);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000e7d4  mov     [rsp-8+arg_8], rbx
0x18000e7d9  mov     [rsp-8+arg_18], rsi
0x18000e7de  push    rbp
0x18000e7df  push    rdi
0x18000e7e0  push    r14
0x18000e7e2  lea     rbp, [rsp-47h]
0x18000e7e7  sub     rsp, 100h
0x18000e7ee  mov     rax, cs:__security_cookie
0x18000e7f5  xor     rax, rsp
0x18000e7f8  mov     [rbp+57h+var_18], rax
0x18000e7fc  mov     rax, [r8]
0x18000e7ff  mov     r14, rdx
0x18000e802  mov     rdi, rcx
0x18000e805  mov     [rbp+57h+var_C0], 0
0x18000e80c  lea     rdx, [rbp+57h+var_C0]
0x18000e810  mov     rcx, r8
0x18000e813  mov     rsi, r8
0x18000e816  mov     rax, [rax+48h]
0x18000e81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e81f  mov     ebx, eax
0x18000e821  test    eax, eax
0x18000e823  jns     short loc_18000E83D
0x18000e825  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e82c  jz      loc_18000E95D
0x18000e832  mov     r8d, 0A6Ah
0x18000e838  jmp     loc_18000E932
0x18000e83d  mov     edx, [rbp+57h+var_C0]
0x18000e840  lea     rax, aLocationwithno; "#LocationWithNoProperties"
0x18000e847  mov     [rbp+57h+var_90], rax
0x18000e84b  lea     rcx, [rbp+57h+var_90]
0x18000e84f  mov     [rsp+110h+var_E8], rcx
0x18000e854  lea     rax, dword_18004809C
0x18000e85b  mov     [rbp+57h+var_88], rax
0x18000e85f  lea     rcx, [rbp+57h+var_40]
0x18000e863  lea     rax, qword_180048748
0x18000e86a  mov     qword ptr [rsp+110h+var_F0], rcx
0x18000e86f  mov     [rbp+57h+var_80], rax
0x18000e873  lea     r9, [rbp+57h+var_B8]
0x18000e877  mov     rax, [r14+20h]
0x18000e87b  mov     r8d, 0Ah
0x18000e881  mov     [rbp+57h+var_70], rax
0x18000e885  mov     rcx, rsi
0x18000e888  lea     rax, byte_180048098
0x18000e88f  mov     [rbp+57h+var_B8], 0
0x18000e896  mov     [rbp+57h+var_68], rax
0x18000e89a  lea     rax, dword_180048094
0x18000e8a1  mov     [rbp+57h+var_60], rax
0x18000e8a5  mov     rax, [r14+38h]
0x18000e8a9  mov     [rbp+57h+var_58], rax
0x18000e8ad  lea     rax, byte_180048090
0x18000e8b4  mov     [rbp+57h+var_50], rax
0x18000e8b8  lea     rax, dword_180048744
0x18000e8bf  mov     [rbp+57h+var_48], rax
0x18000e8c3  mov     rax, [rsi]
0x18000e8c6  mov     [rbp+57h+var_B4], 1
0x18000e8cd  mov     [rbp+57h+var_B0], 2
0x18000e8d4  mov     [rbp+57h+var_AC], 3
0x18000e8db  mov     rax, [rax+58h]
0x18000e8df  mov     [rbp+57h+var_A8], 4
0x18000e8e6  mov     [rbp+57h+var_A4], 5
0x18000e8ed  mov     [rbp+57h+var_A0], 6
0x18000e8f4  mov     [rbp+57h+var_9C], 7
0x18000e8fb  mov     [rbp+57h+var_98], 8
0x18000e902  mov     [rbp+57h+var_94], 9
0x18000e909  mov     [rbp+57h+var_34], 0
0x18000e910  mov     [rbp+57h+var_78], 0
0x18000e918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e91d  mov     ebx, eax
0x18000e91f  test    eax, eax
0x18000e921  jns     short loc_18000E98A
0x18000e923  test    byte ptr cs:g_dwDebugFlags, 3
0x18000e92a  jz      short loc_18000E95D
0x18000e92c  mov     r8d, 0AA3h
0x18000e932  mov     rcx, cs:g_pDebug
0x18000e939  lea     rax, aCfilelistenerS_0; "[CFileListener::SaveChanges] Unable to "...
0x18000e940  mov     dword ptr [rsp+110h+var_E8], ebx
0x18000e944  lea     r9, aCfilelistenerS_1; "CFileListener::SaveChangeAsNodeWithNoPr"...
0x18000e94b  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000e952  mov     qword ptr [rsp+110h+var_F0], rax
0x18000e957  call    cs:__imp_PuDbgPrintW
0x18000e95d  mov     rcx, [rdi+230h]; struct ICatalogErrorLogger2 *
0x18000e964  mov     r8d, 1; unsigned int
0x18000e96a  mov     [rsp+110h+var_E0], 0; unsigned __int16 *
0x18000e973  mov     edx, 0C002C81Ah; unsigned int
0x18000e978  mov     [rsp+110h+var_E8], 0; unsigned __int16 *
0x18000e981  mov     dword ptr [rsp+110h+var_F0], ebx; char
0x18000e985  call    ?LogEvent@@YAJPEAUICatalogErrorLogger2@@KKKKPEAG1111@Z; LogEvent(ICatalogErrorLogger2 *,ulong,ulong,ulong,ulong,ushort *,ushort *,ushort *,ushort *,ushort *)
0x18000e98a  mov     eax, ebx
0x18000e98c  mov     rcx, [rbp+57h+var_18]
0x18000e990  xor     rcx, rsp; StackCookie
0x18000e993  call    __security_check_cookie
0x18000e998  lea     r11, [rsp+110h+var_10]
0x18000e9a0  mov     rbx, [r11+28h]
0x18000e9a4  mov     rsi, [r11+38h]
0x18000e9a8  mov     rsp, r11
0x18000e9ab  pop     r14
0x18000e9ad  pop     rdi
0x18000e9ae  pop     rbp
0x18000e9af  retn
```
