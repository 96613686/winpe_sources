# CImpICommandText::SetCommandText(_GUID const &,ushort const *)

- ea: `0x100109e0`
- end: `0x10010b48`
- name: `?SetCommandText@CImpICommandText@@UAGJABU_GUID@@PBG@Z`
- size: `360`
- prototype: `int(CImpICommandText *__hidden this, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1000ba50`
- `0x1000ba90`
- `0x100109e0`
- `0x100147f0`
- `0x1001c6d0`
- `0x100255a0`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x10010b2c`
- `KERNEL32!LeaveCriticalSection` at `0x10010b2c`
- `KERNEL32!EnterCriticalSection` at `0x10010a24`
- `KERNEL32!EnterCriticalSection` at `0x10010a24`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10010a0e`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x10010a0e`

## pseudocode

```c
int __stdcall CImpICommandText::SetCommandText(
        CImpICommandText *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // esi
  int v4; // eax
  int String; // edi
  const struct _GUID *v6; // edx
  const GUID *v7; // ecx
  const struct _GUID *v8; // edi
  unsigned int v9; // ebx
  bool v10; // cf
  const GUID *v11; // ecx
  unsigned int v12; // edi
  void *v13; // ecx
  const unsigned __int16 *v15; // [esp+0h] [ebp-28h]
  unsigned __int16 **v16; // [esp+4h] [ebp-24h]
  int v17; // [esp+18h] [ebp-10h]

  SetErrorInfo(0, 0);
  v3 = (struct _RTL_CRITICAL_SECTION *)(*((_DWORD *)this + 2) + 248);
  EnterCriticalSection(v3);
  CCommand::CheckForZombieCommandAndFix(*((_DWORD *)this + 2));
  v4 = *((_DWORD *)this + 2);
  if ( *(_DWORD *)(v4 + 80) )
  {
    String = -2147217915;
  }
  else
  {
    String = (*(int (__thiscall **)(_DWORD, _DWORD))(**(_DWORD **)(v4 + 24) + 16))(
               *(_DWORD *)(**(_DWORD **)(v4 + 24) + 16),
               *(_DWORD *)(v4 + 24));
    v17 = String;
    if ( String >= 0 )
    {
      v6 = a2;
      v7 = &DBGUID_SQL;
      v8 = a2;
      v9 = 12;
      while ( v7->Data1 == v8->Data1 )
      {
        v7 = (const GUID *)((char *)v7 + 4);
        v8 = (const struct _GUID *)((char *)v8 + 4);
        v10 = v9 < 4;
        v9 -= 4;
        if ( v10 )
        {
LABEL_11:
          if ( a3 && (v13 = (void *)wcslen(a3)) != 0 )
          {
            if ( *(_DWORD *)(*((_DWORD *)this + 2) + 108) )
            {
              System::Free(v13);
              *(_DWORD *)(*((_DWORD *)this + 2) + 108) = 0;
            }
            String = CopyAndAllocateString(v15, v16);
            if ( String >= 0 )
            {
              *(_DWORD *)(*((_DWORD *)this + 2) + 60) |= 0x20u;
              *(_DWORD *)(*((_DWORD *)this + 2) + 60) &= ~0x10u;
              String = 0;
            }
          }
          else
          {
            String = v17;
            *(_DWORD *)(*((_DWORD *)this + 2) + 60) &= ~0x20u;
          }
          goto LABEL_19;
        }
      }
      v11 = &DBGUID_DEFAULT;
      v12 = 12;
      while ( v11->Data1 == v6->Data1 )
      {
        v11 = (const GUID *)((char *)v11 + 4);
        v6 = (const struct _GUID *)((char *)v6 + 4);
        v10 = v12 < 4;
        v12 -= 4;
        if ( v10 )
          goto LABEL_11;
      }
      String = -2147217898;
    }
  }
LABEL_19:
  if ( v3 )
    LeaveCriticalSection(v3);
  return String;
}

```

## disassembly

```asm
0x100109e0  mov     edi, edi
0x100109e2  push    ebp
0x100109e3  mov     ebp, esp
0x100109e5  push    0FFFFFFFFh
0x100109e7  push    offset ?Hash@CImpIRowsetLocate@@UAGJKKQBKQAPBEQAK2@Z_SEH
0x100109ec  mov     eax, large fs:0
0x100109f2  push    eax
0x100109f3  sub     esp, 0Ch
0x100109f6  push    ebx
0x100109f7  push    esi
0x100109f8  push    edi; unsigned __int16 **
0x100109f9  mov     eax, ___security_cookie
0x100109fe  xor     eax, ebp
0x10010a00  push    eax; unsigned __int16 *
0x10010a01  lea     eax, [ebp+var_C]
0x10010a04  mov     large fs:0, eax
0x10010a0a  push    0; perrinfo
0x10010a0c  push    0; dwReserved
0x10010a0e  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10010a14  mov     ebx, [ebp+this]
0x10010a17  mov     esi, [ebx+8]
0x10010a1a  add     esi, 0F8h
0x10010a20  push    esi; lpCriticalSection
0x10010a21  mov     [ebp+var_14], esi
0x10010a24  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10010a2a  mov     [ebp+var_4], 0
0x10010a31  mov     ecx, [ebx+8]
0x10010a34  call    ?CheckForZombieCommandAndFix@CCommand@@QAGJXZ; CCommand::CheckForZombieCommandAndFix(void)
0x10010a39  mov     eax, [ebx+8]
0x10010a3c  cmp     dword ptr [eax+50h], 0
0x10010a40  jbe     short loc_10010A4C
0x10010a42  mov     edi, 80040E05h
0x10010a47  jmp     loc_10010B27
0x10010a4c  mov     eax, [eax+18h]
0x10010a4f  push    eax
0x10010a50  mov     ecx, [eax]
0x10010a52  mov     edi, [ecx+10h]
0x10010a55  mov     ecx, edi
0x10010a57  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10010a5d  call    edi
0x10010a5f  mov     edi, eax
0x10010a61  mov     [ebp+var_10], edi
0x10010a64  test    edi, edi
0x10010a66  js      loc_10010B27
0x10010a6c  mov     edx, [ebp+arg_4]
0x10010a6f  mov     ecx, offset _DBGUID_SQL
0x10010a74  mov     edi, edx
0x10010a76  mov     ebx, 0Ch
0x10010a7b  nop     dword ptr [eax+eax+00h]
0x10010a80  mov     eax, [ecx]
0x10010a82  cmp     eax, [edi]
0x10010a84  jnz     short loc_10010A93
0x10010a86  add     ecx, 4
0x10010a89  add     edi, 4
0x10010a8c  sub     ebx, 4
0x10010a8f  jnb     short loc_10010A80
0x10010a91  jmp     short loc_10010AB1
0x10010a93  mov     ecx, offset _DBGUID_DEFAULT
0x10010a98  mov     edi, 0Ch
0x10010a9d  nop     dword ptr [eax]
0x10010aa0  mov     eax, [ecx]
0x10010aa2  cmp     eax, [edx]
0x10010aa4  jnz     short loc_10010B22
0x10010aa6  add     ecx, 4
0x10010aa9  add     edx, 4
0x10010aac  sub     edi, 4
0x10010aaf  jnb     short loc_10010AA0
0x10010ab1  mov     edi, [ebp+arg_8]
0x10010ab4  test    edi, edi
0x10010ab6  jz      short loc_10010B13
0x10010ab8  mov     ecx, edi
0x10010aba  lea     edx, [ecx+2]
0x10010abd  nop     dword ptr [eax]
0x10010ac0  mov     ax, [ecx]
0x10010ac3  add     ecx, 2
0x10010ac6  test    ax, ax
0x10010ac9  jnz     short loc_10010AC0
0x10010acb  sub     ecx, edx
0x10010acd  sar     ecx, 1; void *
0x10010acf  jz      short loc_10010B13
0x10010ad1  mov     ebx, [ebp+this]
0x10010ad4  mov     eax, [ebx+8]
0x10010ad7  mov     eax, [eax+6Ch]
0x10010ada  test    eax, eax
0x10010adc  jz      short loc_10010AEE
0x10010ade  push    eax
0x10010adf  call    ?Free@System@@QAEXPAX@Z; System::Free(void *)
0x10010ae4  mov     eax, [ebx+8]
0x10010ae7  mov     dword ptr [eax+6Ch], 0
0x10010aee  mov     edx, [ebx+8]
0x10010af1  mov     ecx, edi
0x10010af3  add     edx, 6Ch ; 'l'
0x10010af6  call    ?CopyAndAllocateString@@YGJPBGPAPAG@Z; CopyAndAllocateString(ushort const *,ushort * *)
0x10010afb  mov     edi, eax
0x10010afd  test    edi, edi
0x10010aff  js      short loc_10010B27
0x10010b01  mov     eax, [ebx+8]
0x10010b04  or      dword ptr [eax+3Ch], 20h
0x10010b08  mov     eax, [ebx+8]
0x10010b0b  and     dword ptr [eax+3Ch], 0FFFFFFEFh
0x10010b0f  xor     edi, edi
0x10010b11  jmp     short loc_10010B27
0x10010b13  mov     eax, [ebp+this]
0x10010b16  mov     edi, [ebp+var_10]
0x10010b19  mov     eax, [eax+8]
0x10010b1c  and     dword ptr [eax+3Ch], 0FFFFFFDFh
0x10010b20  jmp     short loc_10010B27
0x10010b22  mov     edi, 80040E16h
0x10010b27  test    esi, esi
0x10010b29  jz      short loc_10010B32
0x10010b2b  push    esi; lpCriticalSection
0x10010b2c  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10010b32  mov     eax, edi
0x10010b34  mov     ecx, [ebp+var_C]
0x10010b37  mov     large fs:0, ecx
0x10010b3e  pop     ecx
0x10010b3f  pop     edi
0x10010b40  pop     esi
0x10010b41  pop     ebx
0x10010b42  mov     esp, ebp
0x10010b44  pop     ebp
0x10010b45  retn    0Ch
0x1004dd20  lea     ecx, [ebp+var_14]; this
0x1004dd23  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dd2d  nop
0x1004dd2e  nop
0x1004dd2f  mov     edx, [esp-4+arg_4]
0x1004dd33  lea     eax, [edx+0Ch]
0x1004dd36  mov     ecx, [edx-1Ch]
0x1004dd39  xor     ecx, eax; StackCookie
0x1004dd3b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004dd40  mov     eax, offset stru_1004F328
0x1004dd45  jmp     ___CxxFrameHandler3
```
