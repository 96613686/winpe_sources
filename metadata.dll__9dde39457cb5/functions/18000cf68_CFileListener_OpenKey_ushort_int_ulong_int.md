# CFileListener::OpenKey(ushort *,int,ulong *,int *)

- ea: `0x18000cf68`
- end: `0x18000d18c`
- name: `?OpenKey@CFileListener@@AEAAJPEAGHPEAKPEAH@Z`
- size: `548`
- prototype: `__int64 __usercall@<rax>(CFileListener *__hidden this@<rcx>, unsigned __int16 *@<rdx>, int@<r8d>, unsigned int *@<r9>, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d680`

## callees

- `0x18000cf68`
- `0x18000d194`
- `0x18002056c`
- `0x180031010`

## import_xrefs

- `IisRTL!PuDbgPrintW` at `0x18000d132`
- `IisRTL!PuDbgPrintW` at `0x18000d177`
- `IisRTL!PuDbgPrintW` at `0x18000d132`
- `IisRTL!PuDbgPrintW` at `0x18000d177`

## string_xrefs

- `0x18000d08c`: `[CFileListener::OpenKey] Unable to add %s key. IMSAdminBase::AddKey failed with hr = 0x%x.\n`
- `0x18000d119`: `CFileListener::OpenKey`
- `0x18000d15f`: `CFileListener::OpenKey`
- `0x18000d0f4`: `[CFileListener::OpenKey] Unable to open %s key, after successfully adding it. IMSAdminBase::OpenKey failed with hr = 0x%x.\n`
- `0x18000d10d`: `[CFileListener::OpenKey] Successfully added and reopened %s key.\n`
- `0x18000d151`: `[CFileListener::OpenKey] Unable to open %s key. IMSAdminBase::OpenKey failed with unexpected hr = 0x%x.\n`

## pseudocode

```c
__int64 __fastcall CFileListener::OpenKey(CFileListener *this, unsigned __int16 *a2, int a3, unsigned int *a4, int *a5)
{
  int *v5; // rsi
  int v10; // eax
  unsigned int v11; // r9d
  int v12; // edi
  int ChildKey; // eax
  int v14; // eax
  unsigned __int16 *v16; // [rsp+38h] [rbp-50h]
  unsigned __int16 *v17; // [rsp+40h] [rbp-48h]
  unsigned __int16 *v18; // [rsp+48h] [rbp-40h]
  unsigned __int16 *v19; // [rsp+90h] [rbp+8h] BYREF

  v5 = a5;
  v19 = 0;
  if ( a5 )
    *a5 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64, int, unsigned int *))(**((_QWORD **)this + 71) + 280LL))(
          *((_QWORD *)this + 71),
          0,
          a2,
          2,
          30000,
          a4);
  v12 = v10;
  if ( v10 == -2147024893 )
  {
    if ( !a3 )
    {
LABEL_7:
      LogEvent(*((struct ICatalogErrorLogger2 **)this + 70), 0xC002C83D, 1u, v11, 3, a2, 0, v16, v17, v18);
      return (unsigned int)v12;
    }
    ChildKey = CFileListener::OpenParentKeyAndGetChildKey(this, a2, a4, &v19);
    v12 = ChildKey;
    if ( ChildKey >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 71) + 56LL))(
              *((_QWORD *)this + 71),
              *a4,
              v19);
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 71) + 288LL))(*((_QWORD *)this + 71), *a4);
      *a4 = 0;
      if ( v12 >= 0 )
      {
        if ( v5 )
          *v5 = 1;
        v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64, int, unsigned int *))(**((_QWORD **)this + 71) + 280LL))(
                *((_QWORD *)this + 71),
                0,
                a2,
                2,
                30000,
                a4);
        v12 = v14;
        if ( v14 >= 0 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrintW(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\listener.cpp",
              2564,
              "CFileListener::OpenKey",
              L"[CFileListener::OpenKey] Successfully added and reopened %s key.\n",
              a2);
        }
        else if ( (g_dwDebugFlags & 3) != 0 )
        {
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\listener.cpp",
            2557,
            "CFileListener::OpenKey",
            L"[CFileListener::OpenKey] Unable to open %s key, after successfully adding it. IMSAdminBase::OpenKey failed w"
             "ith hr = 0x%x.\n",
            a2,
            v14);
        }
      }
      else if ( (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrintW(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\listener.cpp",
          2537,
          "CFileListener::OpenKey",
          L"[CFileListener::OpenKey] Unable to add %s key. IMSAdminBase::AddKey failed with hr = 0x%x.\n",
          a2,
          v12);
      }
    }
    else if ( ChildKey == -2147024893 )
    {
      goto LABEL_7;
    }
  }
  else if ( v10 < 0 && (g_dwDebugFlags & 3) != 0 )
  {
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\listener.cpp",
      2581,
      "CFileListener::OpenKey",
      L"[CFileListener::OpenKey] Unable to open %s key. IMSAdminBase::OpenKey failed with unexpected hr = 0x%x.\n",
      a2,
      v10);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000cf68  mov     rax, rsp
0x18000cf6b  push    rbx
0x18000cf6c  push    rbp
0x18000cf6d  push    rsi
0x18000cf6e  push    rdi
0x18000cf6f  push    r14
0x18000cf71  push    r15
0x18000cf73  sub     rsp, 58h
0x18000cf77  mov     rsi, [rsp+88h+arg_20]
0x18000cf7f  mov     r14, r9
0x18000cf82  mov     qword ptr [rax+8], 0
0x18000cf8a  mov     r15d, r8d
0x18000cf8d  mov     rbx, rdx
0x18000cf90  mov     rbp, rcx
0x18000cf93  test    rsi, rsi
0x18000cf96  jz      short loc_18000CF9E
0x18000cf98  mov     dword ptr [rsi], 0
0x18000cf9e  mov     rcx, [rcx+238h]
0x18000cfa5  mov     r9d, 2
0x18000cfab  mov     [rsp+88h+var_60], r14
0x18000cfb0  mov     r8, rbx
0x18000cfb3  xor     edx, edx
0x18000cfb5  mov     dword ptr [rsp+88h+var_68], 7530h
0x18000cfbd  mov     rax, [rcx]
0x18000cfc0  mov     rax, [rax+118h]
0x18000cfc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfcc  mov     edi, eax
0x18000cfce  cmp     eax, 80070003h
0x18000cfd3  jnz     loc_18000D13A
0x18000cfd9  test    r15d, r15d
0x18000cfdc  jz      short loc_18000D005
0x18000cfde  lea     r9, [rsp+88h+arg_0]; unsigned __int16 **
0x18000cfe6  mov     r8, r14; unsigned int *
0x18000cfe9  mov     rdx, rbx; unsigned __int16 *
0x18000cfec  mov     rcx, rbp; this
0x18000cfef  call    ?OpenParentKeyAndGetChildKey@CFileListener@@AEAAJPEAGPEAKPEAPEAG@Z; CFileListener::OpenParentKeyAndGetChildKey(ushort *,ulong *,ushort * *)
0x18000cff4  mov     edi, eax
0x18000cff6  test    eax, eax
0x18000cff8  jns     short loc_18000D037
0x18000cffa  cmp     eax, 80070003h
0x18000cfff  jnz     loc_18000D17D
0x18000d005  mov     rcx, [rbp+230h]; struct ICatalogErrorLogger2 *
0x18000d00c  mov     edx, 0C002C83Dh; unsigned int
0x18000d011  mov     [rsp+88h+var_58], 0; unsigned __int16 *
0x18000d01a  mov     r8d, 1; unsigned int
0x18000d020  mov     [rsp+88h+var_60], rbx; unsigned __int16 *
0x18000d025  mov     dword ptr [rsp+88h+var_68], 80070003h; char
0x18000d02d  call    ?LogEvent@@YAJPEAUICatalogErrorLogger2@@KKKKPEAG1111@Z; LogEvent(ICatalogErrorLogger2 *,ulong,ulong,ulong,ulong,ushort *,ushort *,ushort *,ushort *,ushort *)
0x18000d032  jmp     loc_18000D17D
0x18000d037  mov     rcx, [rbp+238h]
0x18000d03e  mov     r8, [rsp+88h+arg_0]
0x18000d046  mov     edx, [r14]
0x18000d049  mov     rax, [rcx]
0x18000d04c  mov     rax, [rax+38h]
0x18000d050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d055  mov     rcx, [rbp+238h]
0x18000d05c  mov     edi, eax
0x18000d05e  mov     rdx, [rcx]
0x18000d061  mov     rax, [rdx+120h]
0x18000d068  mov     edx, [r14]
0x18000d06b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d070  mov     dword ptr [r14], 0
0x18000d077  test    edi, edi
0x18000d079  jns     short loc_18000D09E
0x18000d07b  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d082  jz      loc_18000D17D
0x18000d088  mov     dword ptr [rsp+88h+var_58], edi
0x18000d08c  lea     rax, aCfilelistenerO_4; "[CFileListener::OpenKey] Unable to add "...
0x18000d093  mov     r8d, 9E9h
0x18000d099  jmp     loc_18000D158
0x18000d09e  test    rsi, rsi
0x18000d0a1  jz      short loc_18000D0A9
0x18000d0a3  mov     dword ptr [rsi], 1
0x18000d0a9  mov     rcx, [rbp+238h]
0x18000d0b0  mov     r9d, 2
0x18000d0b6  mov     [rsp+88h+var_60], r14
0x18000d0bb  mov     r8, rbx
0x18000d0be  xor     edx, edx
0x18000d0c0  mov     dword ptr [rsp+88h+var_68], 7530h
0x18000d0c8  mov     rax, [rcx]
0x18000d0cb  mov     rax, [rax+118h]
0x18000d0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0d7  mov     edi, eax
0x18000d0d9  test    eax, eax
0x18000d0db  jns     short loc_18000D0FD
0x18000d0dd  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d0e4  jz      loc_18000D17D
0x18000d0ea  mov     dword ptr [rsp+88h+var_58], eax
0x18000d0ee  mov     r8d, 9FDh
0x18000d0f4  lea     rax, aCfilelistenerO_5; "[CFileListener::OpenKey] Unable to open"...
0x18000d0fb  jmp     short loc_18000D158
0x18000d0fd  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d104  jz      short loc_18000D17D
0x18000d106  mov     rcx, cs:g_pDebug
0x18000d10d  lea     rax, aCfilelistenerO; "[CFileListener::OpenKey] Successfully a"...
0x18000d114  mov     [rsp+88h+var_60], rbx
0x18000d119  lea     r9, aCfilelistenerO_3; "CFileListener::OpenKey"
0x18000d120  mov     r8d, 0A04h
0x18000d126  mov     qword ptr [rsp+88h+var_68], rax
0x18000d12b  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000d132  call    cs:__imp_PuDbgPrintW
0x18000d138  jmp     short loc_18000D17D
0x18000d13a  test    eax, eax
0x18000d13c  jns     short loc_18000D17D
0x18000d13e  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d145  jz      short loc_18000D17D
0x18000d147  mov     dword ptr [rsp+88h+var_58], eax
0x18000d14b  mov     r8d, 0A15h
0x18000d151  lea     rax, aCfilelistenerO_0; "[CFileListener::OpenKey] Unable to open"...
0x18000d158  mov     rcx, cs:g_pDebug
0x18000d15f  lea     r9, aCfilelistenerO_3; "CFileListener::OpenKey"
0x18000d166  mov     [rsp+88h+var_60], rbx
0x18000d16b  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000d172  mov     qword ptr [rsp+88h+var_68], rax
0x18000d177  call    cs:__imp_PuDbgPrintW
0x18000d17d  mov     eax, edi
0x18000d17f  add     rsp, 58h
0x18000d183  pop     r15
0x18000d185  pop     r14
0x18000d187  pop     rdi
0x18000d188  pop     rsi
0x18000d189  pop     rbp
0x18000d18a  pop     rbx
0x18000d18b  retn
```
