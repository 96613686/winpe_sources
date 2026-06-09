# CSecurityDispenser::GetSID(WELL_KNOWN_SID_TYPE,void * *)

- ea: `0x1800179a0`
- end: `0x180017aad`
- name: `?GetSID@CSecurityDispenser@@QEAAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z`
- size: `269`
- prototype: `unsigned int(CSecurityDispenser *__hidden this, enum WELL_KNOWN_SID_TYPE, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018640`

## callees

- `0x1800179a0`
- `0x180017ac0`
- `0x180018ec0`

## string_xrefs

- `0x180017a3e`: `CSecurityDispenser::GetSID`
- `0x180017a2e`: `Failed to create the sid we were looking for\n`
- `0x180017a4c`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`

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
0x1800179a0  push    rbx
0x1800179a2  push    rsi
0x1800179a3  push    rdi
0x1800179a4  push    r14
0x1800179a6  sub     rsp, 48h
0x1800179aa  mov     rbx, r8
0x1800179ad  mov     edi, edx
0x1800179af  mov     r14, rcx
0x1800179b2  test    r8, r8
0x1800179b5  jz      loc_180017A9D
0x1800179bb  cmp     qword ptr [r8], 0
0x1800179bf  jnz     loc_180017A9D
0x1800179c5  xor     esi, esi
0x1800179c7  mov     ecx, edx
0x1800179c9  sub     ecx, 16h
0x1800179cc  jz      short loc_1800179F9
0x1800179ce  sub     ecx, 1
0x1800179d1  jz      short loc_1800179F3
0x1800179d3  sub     ecx, 1
0x1800179d6  jz      short loc_1800179ED
0x1800179d8  cmp     ecx, 2
0x1800179db  jz      short loc_1800179E7
0x1800179dd  mov     esi, 57h ; 'W'
0x1800179e2  jmp     loc_180017A99
0x1800179e7  mov     rax, [r14+18h]
0x1800179eb  jmp     short loc_1800179FC
0x1800179ed  mov     rax, [r14+10h]
0x1800179f1  jmp     short loc_1800179FC
0x1800179f3  mov     rax, [r14+8]
0x1800179f7  jmp     short loc_1800179FC
0x1800179f9  mov     rax, [r14]
0x1800179fc  test    rax, rax
0x1800179ff  jz      short loc_180017A09
0x180017a01  mov     [r8], rax
0x180017a04  jmp     loc_180017A99
0x180017a09  mov     rdx, rbx; void **
0x180017a0c  mov     ecx, edi; enum WELL_KNOWN_SID_TYPE
0x180017a0e  call    ?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z; AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)
0x180017a13  mov     esi, eax
0x180017a15  test    eax, eax
0x180017a17  jz      short loc_180017A64
0x180017a19  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017a20  jz      short loc_180017A99
0x180017a22  test    eax, eax
0x180017a24  jle     short loc_180017A2E
0x180017a26  movzx   eax, ax
0x180017a29  or      eax, 80070000h
0x180017a2e  lea     rcx, aFailedToCreate; "Failed to create the sid we were lookin"...
0x180017a35  mov     dword ptr [rsp+68h+var_38], edi; char
0x180017a39  mov     [rsp+68h+var_40], rcx; char *
0x180017a3e  lea     r9, aCsecuritydispe; "CSecurityDispenser::GetSID"
0x180017a45  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180017a4c  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180017a53  mov     r8d, 26Dh; unsigned int
0x180017a59  mov     [rsp+68h+dwMessageId], eax; dwMessageId
0x180017a5d  call    PuDbgPrintError
0x180017a62  jmp     short loc_180017A99
0x180017a64  sub     edi, 16h
0x180017a67  jz      short loc_180017A93
0x180017a69  sub     edi, 1
0x180017a6c  jz      short loc_180017A8A
0x180017a6e  sub     edi, 1
0x180017a71  jz      short loc_180017A81
0x180017a73  cmp     edi, 2
0x180017a76  jnz     short loc_180017A99
0x180017a78  mov     rax, [rbx]
0x180017a7b  mov     [r14+18h], rax
0x180017a7f  jmp     short loc_180017A99
0x180017a81  mov     rax, [rbx]
0x180017a84  mov     [r14+10h], rax
0x180017a88  jmp     short loc_180017A99
0x180017a8a  mov     rax, [rbx]
0x180017a8d  mov     [r14+8], rax
0x180017a91  jmp     short loc_180017A99
0x180017a93  mov     rax, [rbx]
0x180017a96  mov     [r14], rax
0x180017a99  mov     eax, esi
0x180017a9b  jmp     short loc_180017AA2
0x180017a9d  mov     eax, 57h ; 'W'
0x180017aa2  add     rsp, 48h
0x180017aa6  pop     r14
0x180017aa8  pop     rdi
0x180017aa9  pop     rsi
0x180017aaa  pop     rbx
0x180017aab  retn
```
