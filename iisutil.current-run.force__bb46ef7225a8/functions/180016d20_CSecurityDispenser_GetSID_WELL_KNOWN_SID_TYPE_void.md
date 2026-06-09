# CSecurityDispenser::GetSID(WELL_KNOWN_SID_TYPE,void * *)

- ea: `0x180016d20`
- end: `0x180016e2c`
- name: `?GetSID@CSecurityDispenser@@QEAAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z`
- size: `268`
- prototype: `unsigned int(CSecurityDispenser *__hidden this, enum WELL_KNOWN_SID_TYPE, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800178d0`

## callees

- `0x180016d20`
- `0x180016e40`
- `0x1800180c0`

## string_xrefs

- `0x180016dbe`: `CSecurityDispenser::GetSID`
- `0x180016dae`: `Failed to create the sid we were looking for\n`
- `0x180016dcc`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`

## pseudocode

```c
__int64 __fastcall CSecurityDispenser::GetSID(CSecurityDispenser *this, __int32 a2, void **a3)
{
  unsigned int v6; // esi
  void *v7; // rax
  signed int dwMessageId; // eax
  __int32 v9; // edi
  __int32 v10; // edi
  __int32 v11; // edi

  if ( a3 && !*a3 )
  {
    v6 = 0;
    switch ( a2 )
    {
      case 22:
        v7 = *(void **)this;
        break;
      case 23:
        v7 = (void *)*((_QWORD *)this + 1);
        break;
      case 24:
        v7 = (void *)*((_QWORD *)this + 2);
        break;
      case 26:
        v7 = (void *)*((_QWORD *)this + 3);
        break;
      default:
        return 87;
    }
    if ( v7 )
    {
      *a3 = v7;
    }
    else
    {
      dwMessageId = AllocateAndCreateWellKnownSid(a2, a3);
      v6 = dwMessageId;
      if ( dwMessageId )
      {
        if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
        {
          if ( dwMessageId > 0 )
            dwMessageId = (unsigned __int16)dwMessageId | 0x80070000;
          PuDbgPrintError(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
            0x26Du,
            "CSecurityDispenser::GetSID",
            dwMessageId,
            "Failed to create the sid we were looking for\n",
            a2);
        }
      }
      else
      {
        v9 = a2 - 22;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            v11 = v10 - 1;
            if ( v11 )
            {
              if ( v11 == 2 )
                *((_QWORD *)this + 3) = *a3;
            }
            else
            {
              *((_QWORD *)this + 2) = *a3;
            }
          }
          else
          {
            *((_QWORD *)this + 1) = *a3;
          }
        }
        else
        {
          *(_QWORD *)this = *a3;
        }
      }
    }
    return v6;
  }
  return 87;
}

```

## disassembly

```asm
0x180016d20  push    rbx
0x180016d22  push    rsi
0x180016d23  push    rdi
0x180016d24  push    r14
0x180016d26  sub     rsp, 48h
0x180016d2a  mov     rbx, r8
0x180016d2d  mov     edi, edx
0x180016d2f  mov     r14, rcx
0x180016d32  test    r8, r8
0x180016d35  jz      loc_180016E1D
0x180016d3b  cmp     qword ptr [r8], 0
0x180016d3f  jnz     loc_180016E1D
0x180016d45  xor     esi, esi
0x180016d47  mov     ecx, edx
0x180016d49  sub     ecx, 16h
0x180016d4c  jz      short loc_180016D79
0x180016d4e  sub     ecx, 1
0x180016d51  jz      short loc_180016D73
0x180016d53  sub     ecx, 1
0x180016d56  jz      short loc_180016D6D
0x180016d58  cmp     ecx, 2
0x180016d5b  jz      short loc_180016D67
0x180016d5d  mov     esi, 57h ; 'W'
0x180016d62  jmp     loc_180016E19
0x180016d67  mov     rax, [r14+18h]
0x180016d6b  jmp     short loc_180016D7C
0x180016d6d  mov     rax, [r14+10h]
0x180016d71  jmp     short loc_180016D7C
0x180016d73  mov     rax, [r14+8]
0x180016d77  jmp     short loc_180016D7C
0x180016d79  mov     rax, [r14]
0x180016d7c  test    rax, rax
0x180016d7f  jz      short loc_180016D89
0x180016d81  mov     [r8], rax
0x180016d84  jmp     loc_180016E19
0x180016d89  mov     rdx, rbx; void **
0x180016d8c  mov     ecx, edi; enum WELL_KNOWN_SID_TYPE
0x180016d8e  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180016d93  mov     esi, eax
0x180016d95  test    eax, eax
0x180016d97  jz      short loc_180016DE4
0x180016d99  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180016da0  jz      short loc_180016E19
0x180016da2  test    eax, eax
0x180016da4  jle     short loc_180016DAE
0x180016da6  movzx   eax, ax
0x180016da9  or      eax, 80070000h
0x180016dae  lea     rcx, aFailedToCreate; "Failed to create the sid we were lookin"...
0x180016db5  mov     dword ptr [rsp+68h+var_38], edi; char
0x180016db9  mov     [rsp+68h+var_40], rcx; char *
0x180016dbe  lea     r9, aCsecuritydispe; "CSecurityDispenser::GetSID"
0x180016dc5  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180016dcc  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180016dd3  mov     r8d, 26Dh; unsigned int
0x180016dd9  mov     [rsp+68h+dwMessageId], eax; dwMessageId
0x180016ddd  call    PuDbgPrintError
0x180016de2  jmp     short loc_180016E19
0x180016de4  sub     edi, 16h
0x180016de7  jz      short loc_180016E13
0x180016de9  sub     edi, 1
0x180016dec  jz      short loc_180016E0A
0x180016dee  sub     edi, 1
0x180016df1  jz      short loc_180016E01
0x180016df3  cmp     edi, 2
0x180016df6  jnz     short loc_180016E19
0x180016df8  mov     rax, [rbx]
0x180016dfb  mov     [r14+18h], rax
0x180016dff  jmp     short loc_180016E19
0x180016e01  mov     rax, [rbx]
0x180016e04  mov     [r14+10h], rax
0x180016e08  jmp     short loc_180016E19
0x180016e0a  mov     rax, [rbx]
0x180016e0d  mov     [r14+8], rax
0x180016e11  jmp     short loc_180016E19
0x180016e13  mov     rax, [rbx]
0x180016e16  mov     [r14], rax
0x180016e19  mov     eax, esi
0x180016e1b  jmp     short loc_180016E22
0x180016e1d  mov     eax, 57h ; 'W'
0x180016e22  add     rsp, 48h
0x180016e26  pop     r14
0x180016e28  pop     rdi
0x180016e29  pop     rsi
0x180016e2a  pop     rbx
0x180016e2b  retn
```
