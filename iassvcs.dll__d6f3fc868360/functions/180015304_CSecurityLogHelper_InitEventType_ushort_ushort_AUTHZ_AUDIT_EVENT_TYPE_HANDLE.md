# CSecurityLogHelper::InitEventType(ushort,ushort,AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ * &)

- ea: `0x180015304`
- end: `0x1800154d8`
- name: `?InitEventType@CSecurityLogHelper@@AEAAJGGAEAPEAUAUTHZ_AUDIT_EVENT_TYPE_HANDLE__@@@Z`
- size: `468`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned __int16, unsigned __int16, struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800154e0`

## callees

- `0x180014ba8`
- `0x180015304`
- `0x180017754`

## import_xrefs

- `AUTHZ!AuthziInitializeAuditEventType` at `0x18001540e`
- `AUTHZ!AuthziInitializeAuditEventType` at `0x18001540e`
- `KERNEL32!TryEnterCriticalSection` at `0x18001532f`
- `KERNEL32!TryEnterCriticalSection` at `0x18001532f`
- `KERNEL32!SwitchToThread` at `0x180015344`
- `KERNEL32!SwitchToThread` at `0x180015344`
- `KERNEL32!EnterCriticalSection` at `0x18001534f`
- `KERNEL32!EnterCriticalSection` at `0x18001534f`
- `KERNEL32!LeaveCriticalSection` at `0x1800154c2`
- `KERNEL32!LeaveCriticalSection` at `0x1800154c2`
- `KERNEL32!LeaveCriticalSection` at `0x180018b0b`
- `KERNEL32!GetLastError` at `0x180015418`
- `KERNEL32!GetLastError` at `0x180015418`

## string_xrefs

- `0x180015396`: `Unexpected handle count when initializing security event handle!`
- `0x180015460`: `Unexpected handle count when adding security event handle to array!`

## pseudocode

```c
__int64 __fastcall CSecurityLogHelper::InitEventType(
        LPCRITICAL_SECTION lpCriticalSection,
        unsigned __int16 a2,
        unsigned __int16 a3,
        struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ **a4)
{
  unsigned int v8; // ebx
  int v9; // esi
  unsigned int DebugInfo; // r8d
  __int64 i; // rdx
  signed int LastError; // eax
  __int64 DebugInfo_low; // rax

  v8 = 0;
  v9 = 0;
  while ( !TryEnterCriticalSection(lpCriticalSection) )
  {
    if ( ++v9 >= 100 )
    {
      EnterCriticalSection(lpCriticalSection);
      break;
    }
    SwitchToThread();
  }
  DebugInfo = (unsigned int)lpCriticalSection[14].DebugInfo;
  if ( DebugInfo < 0x20 )
  {
    for ( i = 0; (unsigned int)i < DebugInfo; i = (unsigned int)(i + 1) )
    {
      if ( *((_WORD *)&lpCriticalSection[1].LockCount + 8 * i) == a2 )
      {
        *a4 = (struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *)*((_QWORD *)&lpCriticalSection[1].OwningThread
                                                        + 2 * (unsigned int)i);
        goto LABEL_26;
      }
    }
    if ( (unsigned int)AuthziInitializeAuditEventType(0, 9, a2, a3, a4) )
    {
      DebugInfo_low = LODWORD(lpCriticalSection[14].DebugInfo);
      if ( (unsigned int)DebugInfo_low < 0x20 )
      {
        *((_WORD *)&lpCriticalSection[1].LockCount + 8 * DebugInfo_low) = a2;
        *((_QWORD *)&lpCriticalSection[1].OwningThread + 2 * (unsigned int)LODWORD(lpCriticalSection[14].DebugInfo)++) = *a4;
        v8 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WppDbgPrint("Unexpected handle count when adding security event handle to array!");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_fd755d6b61883af9ca3752193477f27f_Traceguids, "NPSSVC");
        }
        v8 = -2147418113;
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v8 = -2147418113;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("Unexpected handle count when initializing security event handle!");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_fd755d6b61883af9ca3752193477f27f_Traceguids, "NPSSVC");
    }
  }
LABEL_26:
  LeaveCriticalSection(lpCriticalSection);
  return v8;
}

```

## disassembly

```asm
0x180015304  mov     [rsp+arg_0], rcx
0x180015309  push    rbx
0x18001530a  push    rsi
0x18001530b  push    rdi
0x18001530c  push    r12
0x18001530e  push    r14
0x180015310  push    r15
0x180015312  sub     rsp, 48h
0x180015316  mov     r14, r9
0x180015319  movzx   r12d, r8w
0x18001531d  movzx   r15d, dx
0x180015321  mov     rdi, rcx
0x180015324  xor     ebx, ebx
0x180015326  xor     esi, esi
0x180015328  mov     [rsp+78h+var_44], esi
0x18001532c  mov     rcx, rdi; lpCriticalSection
0x18001532f  call    cs:__imp_TryEnterCriticalSection
0x180015335  test    eax, eax
0x180015337  jnz     short loc_180015355
0x180015339  inc     esi
0x18001533b  mov     [rsp+78h+var_44], esi
0x18001533f  cmp     esi, 64h ; 'd'
0x180015342  jge     short loc_18001534C
0x180015344  call    cs:__imp_SwitchToThread
0x18001534a  jmp     short loc_18001532C
0x18001534c  mov     rcx, rdi; lpCriticalSection
0x18001534f  call    cs:__imp_EnterCriticalSection
0x180015355  mov     r8d, [rdi+230h]
0x18001535c  cmp     r8d, 20h ; ' '
0x180015360  jb      short loc_1800153CA
0x180015362  mov     ebx, 8000FFFFh
0x180015367  mov     [rsp+78h+var_48], ebx
0x18001536b  lea     rcx, WPP_GLOBAL_Control
0x180015372  mov     rax, cs:WPP_GLOBAL_Control
0x180015379  cmp     rax, rcx
0x18001537c  jz      loc_1800154BF
0x180015382  cmp     byte ptr [rax+19h], 2
0x180015386  jb      loc_1800154BF
0x18001538c  test    byte ptr [rax+1Ch], 4
0x180015390  jz      loc_1800154BF
0x180015396  lea     rcx, aUnexpectedHand; "Unexpected handle count when initializi"...
0x18001539d  call    WppDbgPrint
0x1800153a2  mov     edx, 0Ah
0x1800153a7  lea     r9, aNpssvc; "NPSSVC"
0x1800153ae  lea     r8, WPP_fd755d6b61883af9ca3752193477f27f_Traceguids
0x1800153b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800153bc  mov     rcx, [rcx+10h]
0x1800153c0  call    WPP_SF_s
0x1800153c5  jmp     loc_1800154BF
0x1800153ca  xor     edx, edx
0x1800153cc  mov     [rsp+78h+var_40], edx
0x1800153d0  cmp     edx, r8d
0x1800153d3  jnb     short loc_1800153FA
0x1800153d5  mov     ecx, edx
0x1800153d7  lea     rax, [rdx+3]
0x1800153db  shl     rax, 4
0x1800153df  cmp     [rax+rdi], r15w
0x1800153e4  jnz     short loc_1800153F6
0x1800153e6  add     rcx, rcx
0x1800153e9  mov     rax, [rdi+rcx*8+38h]
0x1800153ee  mov     [r14], rax
0x1800153f1  jmp     loc_1800154BF
0x1800153f6  inc     edx
0x1800153f8  jmp     short loc_1800153CC
0x1800153fa  mov     edx, 9
0x1800153ff  mov     [rsp+78h+var_58], r14
0x180015404  movzx   r9d, r12w
0x180015408  movzx   r8d, r15w
0x18001540c  xor     ecx, ecx
0x18001540e  call    cs:__imp_AuthziInitializeAuditEventType
0x180015414  test    eax, eax
0x180015416  jnz     short loc_180015436
0x180015418  call    cs:__imp_GetLastError
0x18001541e  mov     ebx, eax
0x180015420  test    eax, eax
0x180015422  jle     loc_1800154BB
0x180015428  movzx   ebx, ax
0x18001542b  or      ebx, 80070000h
0x180015431  jmp     loc_1800154BB
0x180015436  mov     eax, [rdi+230h]
0x18001543c  cmp     eax, 20h ; ' '
0x18001543f  jb      short loc_180015496
0x180015441  lea     rcx, WPP_GLOBAL_Control
0x180015448  mov     rax, cs:WPP_GLOBAL_Control
0x18001544f  cmp     rax, rcx
0x180015452  jz      short loc_18001548F
0x180015454  cmp     byte ptr [rax+19h], 2
0x180015458  jb      short loc_18001548F
0x18001545a  test    byte ptr [rax+1Ch], 4
0x18001545e  jz      short loc_18001548F
0x180015460  lea     rcx, aUnexpectedHand_0; "Unexpected handle count when adding sec"...
0x180015467  call    WppDbgPrint
0x18001546c  mov     edx, 0Bh
0x180015471  lea     r9, aNpssvc; "NPSSVC"
0x180015478  lea     r8, WPP_fd755d6b61883af9ca3752193477f27f_Traceguids
0x18001547f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015486  mov     rcx, [rcx+10h]
0x18001548a  call    WPP_SF_s
0x18001548f  mov     ebx, 8000FFFFh
0x180015494  jmp     short loc_1800154BB
0x180015496  add     rax, 3
0x18001549a  add     rax, rax
0x18001549d  mov     [rdi+rax*8], r15w
0x1800154a2  mov     ecx, [rdi+230h]
0x1800154a8  add     rcx, rcx
0x1800154ab  mov     rax, [r14]
0x1800154ae  mov     [rdi+rcx*8+38h], rax
0x1800154b3  inc     dword ptr [rdi+230h]
0x1800154b9  xor     ebx, ebx
0x1800154bb  mov     [rsp+78h+var_48], ebx
0x1800154bf  mov     rcx, rdi; lpCriticalSection
0x1800154c2  call    cs:__imp_LeaveCriticalSection
0x1800154c8  mov     eax, ebx
0x1800154ca  add     rsp, 48h
0x1800154ce  pop     r15
0x1800154d0  pop     r14
0x1800154d2  pop     r12
0x1800154d4  pop     rdi
0x1800154d5  pop     rsi
0x1800154d6  pop     rbx
0x1800154d7  retn
0x180018af6  push    rbp
0x180018af8  sub     rsp, 30h
0x180018afc  mov     rbp, rdx
0x180018aff  mov     rcx, [rbp+80h]
0x180018b06  add     rsp, 30h
0x180018b0a  pop     rbp
0x180018b0b  jmp     cs:__imp_LeaveCriticalSection
```
