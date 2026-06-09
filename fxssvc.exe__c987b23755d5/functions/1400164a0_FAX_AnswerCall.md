# FAX_AnswerCall

- ea: `0x1400164a0`
- end: `0x140016762`
- name: `FAX_AnswerCall`
- size: `706`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x1400164a0`
- `0x1400452ac`
- `0x14004eb7c`
- `0x140075efc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400166ae`
- `KERNEL32!GetLastError` at `0x140016713`
- `KERNEL32!GetLastError` at `0x140016733`
- `KERNEL32!GetLastError` at `0x1400166ae`
- `KERNEL32!GetLastError` at `0x140016713`
- `KERNEL32!GetLastError` at `0x140016733`
- `KERNEL32!LocalFree` at `0x140016757`
- `KERNEL32!LocalFree` at `0x140016757`
- `KERNEL32!EnterCriticalSection` at `0x1400165e9`
- `KERNEL32!EnterCriticalSection` at `0x1400165e9`
- `KERNEL32!LeaveCriticalSection` at `0x140016649`
- `KERNEL32!LeaveCriticalSection` at `0x140016649`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140016705`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140016705`
- `KERNEL32!LocalAlloc` at `0x1400166a0`
- `KERNEL32!LocalAlloc` at `0x1400166a0`

## pseudocode

```c
__int64 __fastcall FAX_AnswerCall(__int64 a1, unsigned int a2)
{
  unsigned __int64 v2; // rsi
  __int64 result; // rax
  CMapDeviceId *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // eax
  DWORD_PTR v7; // rax
  DWORD LastError; // ebx
  __int64 v9; // r9
  struct _OVERLAPPED *v10; // rax
  struct _OVERLAPPED *v11; // rdi
  HANDLE v12; // rcx
  DWORD v13; // eax
  unsigned int v14; // [rsp+50h] [rbp+18h] BYREF
  int v15; // [rsp+58h] [rbp+20h] BYREF

  v2 = a2;
  v14 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 589, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  v15 = 0;
  result = FaxSvcAccessCheck(0x2000000u, &v15, &v14, 1);
  if ( !(_DWORD)result )
  {
    if ( (v14 & 0xE03FF) == 0 )
      return 5;
    if ( !(unsigned int)CanAccessUnAssignedFaxes(v14, 1) )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 5;
      }
      v5 = 590;
      goto LABEL_12;
    }
    v14 = 0;
    v6 = IsLocalRPCConnectionNP(&v14);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 591, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v6);
      }
      return 5;
    }
    if ( !v14 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 5;
      }
      v5 = 592;
LABEL_12:
      WPP_SF_(*((_QWORD *)v4 + 2), v5, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
      return 5;
    }
    EnterCriticalSection(&g_CsLine);
    v7 = g_TapiLinesListHead;
    if ( g_TapiLinesListHead )
    {
      while ( (DWORD_PTR *)v7 != &g_TapiLinesListHead )
      {
        if ( *(_DWORD *)(v7 + 24) == (_DWORD)v2 )
        {
          if ( !v7 )
            break;
          v9 = *(unsigned int *)(v7 + 72);
          if ( (_DWORD)v9 == 537919488 )
          {
            v10 = (struct _OVERLAPPED *)LocalAlloc(0x40u, 0x28u);
            v11 = v10;
            if ( v10 )
            {
              v12 = g_TapiCompletionPort;
              LastError = 0;
              v10->Pointer = (PVOID)v2;
              if ( !PostQueuedCompletionStatus(v12, 0x28u, 0x80000005, v10) )
              {
                LastError = GetLastError();
                if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v13 = GetLastError();
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    596,
                    &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                    v13);
                }
                LocalFree(v11);
              }
            }
            else
            {
              LastError = GetLastError();
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 595, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
              }
            }
          }
          else
          {
            LastError = 170;
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 594, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v9);
            }
          }
          goto LABEL_34;
        }
        v7 = *(_QWORD *)v7;
      }
    }
    LastError = 87;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        593,
        &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
        (unsigned int)v2);
    }
LABEL_34:
    LeaveCriticalSection(&g_CsLine);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x1400164a0  mov     [rsp+arg_0], rbx
0x1400164a5  mov     [rsp+arg_8], rsi
0x1400164aa  push    rdi
0x1400164ab  push    r12
0x1400164ad  push    r15
0x1400164af  sub     rsp, 20h
0x1400164b3  mov     esi, edx
0x1400164b5  mov     [rsp+38h+arg_10], 0
0x1400164bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400164c4  lea     r15, WPP_GLOBAL_Control
0x1400164cb  lea     r12, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x1400164d2  cmp     rcx, r15
0x1400164d5  jz      short loc_1400164F4
0x1400164d7  test    byte ptr [rcx+1Ch], 4
0x1400164db  jz      short loc_1400164F4
0x1400164dd  cmp     byte ptr [rcx+19h], 5
0x1400164e1  jb      short loc_1400164F4
0x1400164e3  mov     rcx, [rcx+10h]
0x1400164e7  mov     edx, 24Dh
0x1400164ec  mov     r8, r12
0x1400164ef  call    WPP_SF_
0x1400164f4  mov     ebx, 1
0x1400164f9  mov     [rsp+38h+arg_18], 0
0x140016501  mov     r9d, ebx; int
0x140016504  lea     r8, [rsp+38h+arg_10]; unsigned int *
0x140016509  lea     rdx, [rsp+38h+arg_18]; int *
0x14001650e  mov     ecx, 2000000h; unsigned int
0x140016513  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x140016518  test    eax, eax
0x14001651a  jnz     short loc_140016561
0x14001651c  mov     ecx, [rsp+38h+arg_10]; unsigned int
0x140016520  test    ecx, 0E03FFh
0x140016526  jz      short loc_14001655C
0x140016528  mov     edx, ebx; int
0x14001652a  call    ?CanAccessUnAssignedFaxes@@YAHKH@Z; CanAccessUnAssignedFaxes(ulong,int)
0x14001652f  test    eax, eax
0x140016531  jnz     short loc_140016575
0x140016533  mov     rcx, cs:WPP_GLOBAL_Control
0x14001653a  cmp     rcx, r15
0x14001653d  jz      short loc_14001655C
0x14001653f  test    byte ptr [rcx+1Ch], 4
0x140016543  jz      short loc_14001655C
0x140016545  cmp     byte ptr [rcx+19h], 2
0x140016549  jb      short loc_14001655C
0x14001654b  mov     edx, 24Eh
0x140016550  mov     rcx, [rcx+10h]
0x140016554  mov     r8, r12
0x140016557  call    WPP_SF_
0x14001655c  mov     eax, 5
0x140016561  mov     rbx, [rsp+38h+arg_0]
0x140016566  mov     rsi, [rsp+38h+arg_8]
0x14001656b  add     rsp, 20h
0x14001656f  pop     r15
0x140016571  pop     r12
0x140016573  pop     rdi
0x140016574  retn
0x140016575  lea     rcx, [rsp+38h+arg_10]
0x14001657a  mov     [rsp+38h+arg_10], 0
0x140016582  call    IsLocalRPCConnectionNP
0x140016587  test    eax, eax
0x140016589  jz      short loc_1400165B9
0x14001658b  mov     rcx, cs:WPP_GLOBAL_Control
0x140016592  cmp     rcx, r15
0x140016595  jz      short loc_14001655C
0x140016597  test    byte ptr [rcx+1Ch], 4
0x14001659b  jz      short loc_14001655C
0x14001659d  cmp     byte ptr [rcx+19h], 2
0x1400165a1  jb      short loc_14001655C
0x1400165a3  mov     rcx, [rcx+10h]
0x1400165a7  mov     edx, 24Fh
0x1400165ac  mov     r9d, eax
0x1400165af  mov     r8, r12
0x1400165b2  call    WPP_SF_d
0x1400165b7  jmp     short loc_14001655C
0x1400165b9  cmp     [rsp+38h+arg_10], 0
0x1400165be  jnz     short loc_1400165E2
0x1400165c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400165c7  cmp     rcx, r15
0x1400165ca  jz      short loc_14001655C
0x1400165cc  test    byte ptr [rcx+1Ch], 4
0x1400165d0  jz      short loc_14001655C
0x1400165d2  cmp     byte ptr [rcx+19h], 2
0x1400165d6  jb      short loc_14001655C
0x1400165d8  mov     edx, 250h
0x1400165dd  jmp     loc_140016550
0x1400165e2  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1400165e9  call    cs:__imp_EnterCriticalSection
0x1400165ef  mov     rax, cs:?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x1400165f6  test    rax, rax
0x1400165f9  jz      short loc_140016611
0x1400165fb  lea     rcx, ?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x140016602  jmp     short loc_14001660C
0x140016604  cmp     [rax+18h], esi
0x140016607  jz      short loc_140016656
0x140016609  mov     rax, [rax]
0x14001660c  cmp     rax, rcx
0x14001660f  jnz     short loc_140016604
0x140016611  mov     ebx, 57h ; 'W'
0x140016616  mov     rcx, cs:WPP_GLOBAL_Control
0x14001661d  cmp     rcx, r15
0x140016620  jz      short loc_140016642
0x140016622  test    byte ptr [rcx+1Ch], 4
0x140016626  jz      short loc_140016642
0x140016628  cmp     byte ptr [rcx+19h], 2
0x14001662c  jb      short loc_140016642
0x14001662e  mov     rcx, [rcx+10h]
0x140016632  mov     edx, 251h
0x140016637  mov     r9d, esi
0x14001663a  mov     r8, r12
0x14001663d  call    WPP_SF_d
0x140016642  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140016649  call    cs:__imp_LeaveCriticalSection
0x14001664f  mov     eax, ebx
0x140016651  jmp     loc_140016561
0x140016656  test    rax, rax
0x140016659  jz      short loc_140016611
0x14001665b  mov     r9d, [rax+48h]
0x14001665f  cmp     r9d, 20100000h
0x140016666  jz      short loc_140016698
0x140016668  mov     ebx, 0AAh
0x14001666d  mov     rcx, cs:WPP_GLOBAL_Control
0x140016674  cmp     rcx, r15
0x140016677  jz      short loc_140016642
0x140016679  test    byte ptr [rcx+1Ch], 4
0x14001667d  jz      short loc_140016642
0x14001667f  cmp     byte ptr [rcx+19h], 2
0x140016683  jb      short loc_140016642
0x140016685  mov     rcx, [rcx+10h]
0x140016689  mov     edx, 252h
0x14001668e  mov     r8, r12
0x140016691  call    WPP_SF_d
0x140016696  jmp     short loc_140016642
0x140016698  mov     edx, 28h ; '('; uBytes
0x14001669d  lea     ecx, [rdx+18h]; uFlags
0x1400166a0  call    cs:__imp_LocalAlloc
0x1400166a6  mov     rdi, rax
0x1400166a9  test    rax, rax
0x1400166ac  jnz     short loc_1400166EC
0x1400166ae  call    cs:__imp_GetLastError
0x1400166b4  mov     ebx, eax
0x1400166b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400166bd  cmp     rcx, r15
0x1400166c0  jz      short loc_140016642
0x1400166c2  test    byte ptr [rcx+1Ch], 4
0x1400166c6  jz      loc_140016642
0x1400166cc  cmp     byte ptr [rcx+19h], 2
0x1400166d0  jb      loc_140016642
0x1400166d6  mov     rcx, [rcx+10h]
0x1400166da  mov     edx, 253h
0x1400166df  mov     r8, r12
0x1400166e2  call    WPP_SF_
0x1400166e7  jmp     loc_140016642
0x1400166ec  mov     rcx, cs:?g_TapiCompletionPort@@3PEAXEA; CompletionPort
0x1400166f3  xor     ebx, ebx
0x1400166f5  mov     r9, rdi; lpOverlapped
0x1400166f8  mov     [rax+10h], rsi
0x1400166fc  mov     r8d, 80000005h; dwCompletionKey
0x140016702  lea     edx, [rbx+28h]; dwNumberOfBytesTransferred
0x140016705  call    cs:__imp_PostQueuedCompletionStatus
0x14001670b  test    eax, eax
0x14001670d  jnz     loc_140016642
0x140016713  call    cs:__imp_GetLastError
0x140016719  mov     ebx, eax
0x14001671b  mov     rax, cs:WPP_GLOBAL_Control
0x140016722  cmp     rax, r15
0x140016725  jz      short loc_140016754
0x140016727  test    byte ptr [rax+1Ch], 4
0x14001672b  jz      short loc_140016754
0x14001672d  cmp     byte ptr [rax+19h], 2
0x140016731  jb      short loc_140016754
0x140016733  call    cs:__imp_GetLastError
0x140016739  mov     rcx, cs:WPP_GLOBAL_Control
0x140016740  mov     edx, 254h
0x140016745  mov     r9d, eax
0x140016748  mov     r8, r12
0x14001674b  mov     rcx, [rcx+10h]
0x14001674f  call    WPP_SF_d
0x140016754  mov     rcx, rdi; hMem
0x140016757  call    cs:__imp_LocalFree
0x14001675d  jmp     loc_140016642
```
