# CActiveXInstallBroker::InitializeAxInstaller(int,ushort *,ulong,IUnknown *,ushort * *)

- ea: `0x140004aa0`
- end: `0x140004c81`
- name: `?InitializeAxInstaller@CActiveXInstallBroker@@QEAAJHPEAGKPEAUIUnknown@@PEAPEAG@Z`
- size: `481`
- prototype: `__int64 __usercall@<rax>(CActiveXInstallBroker *__hidden this@<rcx>, int@<edx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, struct IUnknown *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140007e20`
- `0x140007ed0`

## callees

- `0x140004aa0`
- `0x1400059f0`
- `0x1400096b4`
- `0x140009738`
- `0x14000ba88`
- `0x140011010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140004c5d`
- `KERNEL32!LeaveCriticalSection` at `0x140004c5d`
- `KERNEL32!EnterCriticalSection` at `0x140004ae0`
- `KERNEL32!EnterCriticalSection` at `0x140004ae0`
- `OLEAUT32!__imp_SysAllocString` at `0x140004b48`
- `OLEAUT32!__imp_SysAllocString` at `0x140004b73`
- `OLEAUT32!__imp_SysAllocString` at `0x140004b48`
- `OLEAUT32!__imp_SysAllocString` at `0x140004b73`
- `OLEAUT32!__imp_SysFreeString` at `0x140004c1d`
- `OLEAUT32!__imp_SysFreeString` at `0x140004c31`
- `OLEAUT32!__imp_SysFreeString` at `0x140004c45`
- `OLEAUT32!__imp_SysFreeString` at `0x140004c1d`
- `OLEAUT32!__imp_SysFreeString` at `0x140004c31`
- `OLEAUT32!__imp_SysFreeString` at `0x140004c45`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::InitializeAxInstaller(
        CActiveXInstallBroker *this,
        int a2,
        unsigned __int16 *a3,
        int a4,
        struct IUnknown *a5,
        unsigned __int16 **a6)
{
  OLECHAR *v6; // rsi
  OLECHAR *v7; // r15
  OLECHAR *v8; // r14
  struct _RTL_CRITICAL_SECTION *v12; // r12
  struct IUnknown *v13; // r13
  signed int IsSystemOrAdminWithHighIL; // eax
  signed int TempDir; // edi
  unsigned __int16 **v16; // rax
  OLECHAR *psz; // [rsp+60h] [rbp+8h] BYREF
  int v19; // [rsp+68h] [rbp+10h]
  int v20; // [rsp+78h] [rbp+20h]

  v20 = a4;
  v19 = a2;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  psz = 0;
  if ( !*(_DWORD *)this )
    goto LABEL_17;
  v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( a6 )
  {
    v13 = a5;
    if ( !a2 )
    {
LABEL_10:
      v7 = SysAllocString(a3);
      TempDir = CreateUuidString(&psz);
      v6 = psz;
      if ( TempDir < 0 )
      {
LABEL_18:
        if ( v7 )
          SysFreeString(v7);
        if ( v6 )
          SysFreeString(v6);
        if ( v8 )
          SysFreeString(v8);
        goto LABEL_24;
      }
      v8 = SysAllocString(psz);
      if ( v8 )
      {
        CActiveXInstallBroker::Reset((BSTR *)this, 1);
        TempDir = CreateTempDir((char *)this + 160);
        if ( TempDir >= 0 )
        {
          if ( !v13
            || (TempDir = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))v13->lpVtbl->QueryInterface)(
                            v13,
                            &GUID_1823e7ba_ec36_447a_9b2e_b4912e15afe7,
                            (char *)this + 152),
                TempDir >= 0) )
          {
            *((_DWORD *)this + 30) = v20;
            *((_DWORD *)this + 35) = v19;
            v16 = a6;
            *((_QWORD *)this + 7) = v7;
            *((_QWORD *)this + 8) = v8;
            *((_DWORD *)this + 12) = 1;
            *((_DWORD *)this + 36) = 1;
            *((_DWORD *)this + 34) = 1;
            *v16 = v6;
            goto LABEL_25;
          }
        }
        goto LABEL_18;
      }
LABEL_17:
      TempDir = -2147024882;
      goto LABEL_18;
    }
    if ( (g_fRunningAsSystem || g_fRunningAsAdminWithHighIL) && a5 )
    {
      IsSystemOrAdminWithHighIL = VerifyCallerIsSystemOrAdminWithHighIL();
      TempDir = IsSystemOrAdminWithHighIL;
      if ( IsSystemOrAdminWithHighIL )
      {
        if ( IsSystemOrAdminWithHighIL == 1 )
          TempDir = -2147024891;
        goto LABEL_24;
      }
      goto LABEL_10;
    }
  }
  TempDir = -2147024809;
LABEL_24:
  v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
LABEL_25:
  if ( *(_DWORD *)this )
    LeaveCriticalSection(v12);
  return (unsigned int)TempDir;
}

```

## disassembly

```asm
0x140004aa0  mov     rax, rsp
0x140004aa3  mov     [rax+18h], rbx
0x140004aa7  mov     [rax+20h], r9d
0x140004aab  mov     [rax+10h], edx
0x140004aae  push    rbp
0x140004aaf  push    rsi
0x140004ab0  push    rdi
0x140004ab1  push    r12
0x140004ab3  push    r13
0x140004ab5  push    r14
0x140004ab7  push    r15
0x140004ab9  sub     rsp, 20h
0x140004abd  xor     esi, esi
0x140004abf  xor     r15d, r15d
0x140004ac2  xor     r14d, r14d
0x140004ac5  mov     [rax+8], rsi
0x140004ac9  mov     rbp, r8
0x140004acc  mov     edi, edx
0x140004ace  mov     rbx, rcx
0x140004ad1  cmp     [rcx], esi
0x140004ad3  jz      loc_140004C10
0x140004ad9  lea     r12, [rcx+8]
0x140004add  mov     rcx, r12; lpCriticalSection
0x140004ae0  call    cs:__imp_EnterCriticalSection
0x140004ae7  nop     dword ptr [rax+rax+00h]
0x140004aec  cmp     [rsp+58h+arg_28], rsi
0x140004af4  jz      loc_140004C09
0x140004afa  mov     r13, [rsp+58h+arg_20]
0x140004b02  test    edi, edi
0x140004b04  jz      short loc_140004B45
0x140004b06  cmp     cs:?g_fRunningAsSystem@@3HA, esi; int g_fRunningAsSystem
0x140004b0c  jnz     short loc_140004B1A
0x140004b0e  cmp     cs:?g_fRunningAsAdminWithHighIL@@3HA, esi; int g_fRunningAsAdminWithHighIL
0x140004b14  jz      loc_140004C09
0x140004b1a  test    r13, r13
0x140004b1d  jz      loc_140004C09
0x140004b23  call    ?VerifyCallerIsSystemOrAdminWithHighIL@@YAJXZ; VerifyCallerIsSystemOrAdminWithHighIL(void)
0x140004b28  mov     edi, eax
0x140004b2a  test    eax, eax
0x140004b2c  jz      short loc_140004B45
0x140004b2e  mov     ebp, 1
0x140004b33  cmp     eax, ebp
0x140004b35  jnz     loc_140004C51
0x140004b3b  mov     edi, 80070005h
0x140004b40  jmp     loc_140004C51
0x140004b45  mov     rcx, rbp; psz
0x140004b48  call    cs:__imp_SysAllocString
0x140004b4f  nop     dword ptr [rax+rax+00h]
0x140004b54  lea     rcx, [rsp+58h+psz]; unsigned __int16 **
0x140004b59  mov     r15, rax
0x140004b5c  call    ?CreateUuidString@@YAJPEAPEAG@Z; CreateUuidString(ushort * *)
0x140004b61  mov     edi, eax
0x140004b63  mov     rsi, [rsp+58h+psz]
0x140004b68  test    eax, eax
0x140004b6a  js      loc_140004C15
0x140004b70  mov     rcx, rsi; psz
0x140004b73  call    cs:__imp_SysAllocString
0x140004b7a  nop     dword ptr [rax+rax+00h]
0x140004b7f  mov     r14, rax
0x140004b82  test    rax, rax
0x140004b85  jz      loc_140004C10
0x140004b8b  mov     ebp, 1
0x140004b90  mov     rcx, rbx; this
0x140004b93  mov     edx, ebp; int
0x140004b95  call    ?Reset@CActiveXInstallBroker@@AEAAXH@Z; CActiveXInstallBroker::Reset(int)
0x140004b9a  lea     rcx, [rbx+0A0h]; char *
0x140004ba1  call    ?CreateTempDir@@YAJPEADK@Z; CreateTempDir(char *,ulong)
0x140004ba6  mov     edi, eax
0x140004ba8  test    eax, eax
0x140004baa  js      short loc_140004C15
0x140004bac  test    r13, r13
0x140004baf  jz      short loc_140004BD4
0x140004bb1  mov     rax, [r13+0]
0x140004bb5  lea     r8, [rbx+98h]
0x140004bbc  lea     rdx, _GUID_1823e7ba_ec36_447a_9b2e_b4912e15afe7
0x140004bc3  mov     rcx, r13
0x140004bc6  mov     rax, [rax]
0x140004bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004bce  mov     edi, eax
0x140004bd0  test    eax, eax
0x140004bd2  js      short loc_140004C15
0x140004bd4  mov     eax, [rsp+58h+arg_18]
0x140004bd8  mov     [rbx+78h], eax
0x140004bdb  mov     eax, [rsp+58h+arg_8]
0x140004bdf  mov     [rbx+8Ch], eax
0x140004be5  mov     rax, [rsp+58h+arg_28]
0x140004bed  mov     [rbx+38h], r15
0x140004bf1  mov     [rbx+40h], r14
0x140004bf5  mov     [rbx+30h], ebp
0x140004bf8  mov     [rbx+90h], ebp
0x140004bfe  mov     [rbx+88h], ebp
0x140004c04  mov     [rax], rsi
0x140004c07  jmp     short loc_140004C55
0x140004c09  mov     edi, 80070057h
0x140004c0e  jmp     short loc_140004C51
0x140004c10  mov     edi, 8007000Eh
0x140004c15  test    r15, r15
0x140004c18  jz      short loc_140004C29
0x140004c1a  mov     rcx, r15; bstrString
0x140004c1d  call    cs:__imp_SysFreeString
0x140004c24  nop     dword ptr [rax+rax+00h]
0x140004c29  test    rsi, rsi
0x140004c2c  jz      short loc_140004C3D
0x140004c2e  mov     rcx, rsi; bstrString
0x140004c31  call    cs:__imp_SysFreeString
0x140004c38  nop     dword ptr [rax+rax+00h]
0x140004c3d  test    r14, r14
0x140004c40  jz      short loc_140004C51
0x140004c42  mov     rcx, r14; bstrString
0x140004c45  call    cs:__imp_SysFreeString
0x140004c4c  nop     dword ptr [rax+rax+00h]
0x140004c51  lea     r12, [rbx+8]
0x140004c55  cmp     dword ptr [rbx], 0
0x140004c58  jz      short loc_140004C69
0x140004c5a  mov     rcx, r12; lpCriticalSection
0x140004c5d  call    cs:__imp_LeaveCriticalSection
0x140004c64  nop     dword ptr [rax+rax+00h]
0x140004c69  mov     rbx, [rsp+58h+arg_10]
0x140004c6e  mov     eax, edi
0x140004c70  add     rsp, 20h
0x140004c74  pop     r15
0x140004c76  pop     r14
0x140004c78  pop     r13
0x140004c7a  pop     r12
0x140004c7c  pop     rdi
0x140004c7d  pop     rsi
0x140004c7e  pop     rbp
0x140004c7f  retn
```
