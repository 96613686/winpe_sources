# CImpICommandText::Cancel(void)

- ea: `0x1000fc70`
- end: `0x1000fce6`
- name: `?Cancel@CImpICommandText@@UAGJXZ`
- size: `118`
- prototype: `int __stdcall(CImpICommandText *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x1000fc70`
- `0x100147f0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1000fccb`
- `KERNEL32!LeaveCriticalSection` at `0x1000fccb`
- `KERNEL32!EnterCriticalSection` at `0x1000fcb1`
- `KERNEL32!EnterCriticalSection` at `0x1000fcb1`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000fc9b`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x1000fc9b`

## pseudocode

```c
int __stdcall CImpICommandText::Cancel(CImpICommandText *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // esi

  SetErrorInfo(0, 0);
  v1 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 248);
  EnterCriticalSection(v1);
  CCommand::CheckForZombieCommandAndFix(*((_DWORD *)this + 2));
  if ( v1 )
    LeaveCriticalSection(v1);
  return 0;
}

```

## disassembly

```asm
0x1000fc70  mov     edi, edi
0x1000fc72  push    ebp
0x1000fc73  mov     ebp, esp
0x1000fc75  push    0FFFFFFFFh
0x1000fc77  push    offset ?CreateTable@CImpITableDef@@UAGJPAUIUnknown@@PAUtagDBID@@KQBUtagDBCOLUMNDESC@@ABU_GUID@@KQAUtagDBPROPSET@@PAPAU3@PAPAU2@@Z_SEH
0x1000fc7c  mov     eax, large fs:0
0x1000fc82  push    eax
0x1000fc83  push    ecx
0x1000fc84  push    esi
0x1000fc85  push    edi
0x1000fc86  mov     eax, ___security_cookie
0x1000fc8b  xor     eax, ebp
0x1000fc8d  push    eax; this
0x1000fc8e  lea     eax, [ebp+var_C]
0x1000fc91  mov     large fs:0, eax
0x1000fc97  push    0; perrinfo
0x1000fc99  push    0; dwReserved
0x1000fc9b  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x1000fca1  mov     edi, [ebp+this]
0x1000fca4  mov     esi, [edi+8]
0x1000fca7  add     esi, 0F8h
0x1000fcad  push    esi; lpCriticalSection
0x1000fcae  mov     [ebp+var_10], esi
0x1000fcb1  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000fcb7  mov     [ebp+var_4], 0
0x1000fcbe  mov     ecx, [edi+8]
0x1000fcc1  call    ?CheckForZombieCommandAndFix@CCommand@@QAGJXZ; CCommand::CheckForZombieCommandAndFix(void)
0x1000fcc6  test    esi, esi
0x1000fcc8  jz      short loc_1000FCD1
0x1000fcca  push    esi; lpCriticalSection
0x1000fccb  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000fcd1  xor     eax, eax
0x1000fcd3  mov     ecx, [ebp+var_C]
0x1000fcd6  mov     large fs:0, ecx
0x1000fcdd  pop     ecx
0x1000fcde  pop     edi
0x1000fcdf  pop     esi
0x1000fce0  mov     esp, ebp
0x1000fce2  pop     ebp
0x1000fce3  retn    4
0x1004df10  lea     ecx, [ebp+var_10]; this
0x1004df13  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004df1d  nop
0x1004df1e  nop
0x1004df1f  mov     edx, [esp-4+arg_4]
0x1004df23  lea     eax, [edx+0Ch]
0x1004df26  mov     ecx, [edx-10h]
0x1004df29  xor     ecx, eax; StackCookie
0x1004df2b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004df30  mov     eax, offset stru_1004F4C4
0x1004df35  jmp     ___CxxFrameHandler3
```
