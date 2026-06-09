# PlaiIsAdminToken(int *)

- ea: `0x18001153c`
- end: `0x18001186a`
- name: `?PlaiIsAdminToken@@YAJPEAH@Z`
- size: `814`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007b9a0`
- `0x1800edc58`
- `0x1800f1dec`
- `0x18010a344`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x18001153c`
- `0x18002b3a0`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011819`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011587`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180011587`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011579`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011579`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001180f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001180f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180011714`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180011714`

## string_xrefs

- `0x1800116c6`: `PlaiIsAdminToken`
- `0x1800117c8`: `PlaiIsAdminToken`

## pseudocode

```c
__int64 __fastcall PlaiIsAdminToken(PBOOL IsMember)
{
  HANDLE ProcessHeap; // rax
  LPVOID v3; // rax
  int v4; // edx
  unsigned __int64 v5; // rcx
  void *v6; // rdi
  int v7; // ebx
  __int64 v8; // rax
  DWORD LastError; // eax
  int v10; // eax
  __int64 v11; // rax
  DWORD v12; // eax
  int v14; // [rsp+70h] [rbp-90h] BYREF
  __int64 v15; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbSid; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v17; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v18[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v19[64]; // [rsp+110h] [rbp+10h] BYREF

  cbSid = 68;
  ProcessHeap = GetProcessHeap();
  v3 = HeapAlloc(ProcessHeap, 0, 0x44u);
  v4 = xmmword_180169738;
  v5 = qword_180169748;
  v15 = 68;
  v17 = v3;
  v6 = v3;
  v14 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
  {
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ALLOC, 4, byte_180147320, 1, &v14, 4, &v17, 8);
    v5 = qword_180169748;
    v4 = xmmword_180169738;
  }
  if ( v6 )
  {
    if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v6, &cbSid) )
    {
      LastError = GetLastError();
      v10 = PlaiHResultFromWin32(LastError);
      v7 = v10;
      if ( v10 < 0 )
      {
        LODWORD(v15) = 0;
        v14 = v10;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v19, 0x4000000000000800uLL);
          v11 = -1;
          do
            ++v11;
          while ( v19[v11] );
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v14, 4, byte_180147320, 1, &v15, 4);
        }
        goto LABEL_24;
      }
    }
    if ( !CheckTokenMembership(0, v6, IsMember) )
    {
      v12 = GetLastError();
      v7 = PlaiHResultFromWin32(v12);
      if ( v7 >= 0 )
      {
LABEL_24:
        PlaiFree(v6, 1);
        return (unsigned int)v7;
      }
      *IsMember = 0;
    }
    v7 = 0;
    goto LABEL_24;
  }
  v14 = 0;
  v7 = -2147024882;
  LODWORD(v15) = -2147024882;
  if ( v4 && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0 && v5 == (v5 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v18, 0x4000000000000800uLL);
    v8 = -1;
    do
      ++v8;
    while ( v18[v8] );
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v15, 4, byte_180147320, 1, &v14, 4);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001153c  mov     [rsp-8+arg_8], rbx
0x180011541  mov     [rsp-8+arg_10], rsi
0x180011546  push    rbp
0x180011547  push    rdi
0x180011548  push    r12
0x18001154a  push    r14
0x18001154c  push    r15
0x18001154e  lea     rbp, [rsp-0A0h]
0x180011556  sub     rsp, 1A0h
0x18001155d  mov     rax, cs:__security_cookie
0x180011564  xor     rax, rsp
0x180011567  mov     [rbp+0C0h+var_30], rax
0x18001156e  mov     ebx, 44h ; 'D'
0x180011573  mov     rsi, rcx
0x180011576  mov     [rbp+0C0h+cbSid], ebx
0x180011579  call    cs:__imp_GetProcessHeap
0x18001157f  mov     r8d, ebx; dwBytes
0x180011582  xor     edx, edx; dwFlags
0x180011584  mov     rcx, rax; hHeap
0x180011587  call    cs:__imp_HeapAlloc
0x18001158d  mov     edx, dword ptr cs:xmmword_180169738
0x180011593  lea     r15d, [rbx-40h]
0x180011597  mov     rcx, cs:qword_180169748
0x18001159e  lea     r12d, [rbx-43h]
0x1800115a2  xor     r14d, r14d
0x1800115a5  mov     [rsp+1C0h+var_148], rbx
0x1800115aa  mov     [rbp+0C0h+var_138], rax
0x1800115ae  mov     rdi, rax
0x1800115b1  mov     [rsp+1C0h+var_150], r14d
0x1800115b6  test    edx, edx
0x1800115b8  jz      short loc_180011636
0x1800115ba  mov     r8, 4000000000000200h
0x1800115c4  test    qword ptr cs:xmmword_180169738+8, r8
0x1800115cb  jz      short loc_180011636
0x1800115cd  mov     rax, rcx
0x1800115d0  and     rax, r8
0x1800115d3  cmp     rcx, rax
0x1800115d6  jnz     short loc_180011636
0x1800115d8  lea     ecx, [rbx-3Ch]
0x1800115db  mov     r8d, r15d
0x1800115de  mov     [rsp+1C0h+var_170], rcx
0x1800115e3  lea     rax, [rsp+1C0h+var_148]
0x1800115e8  mov     [rsp+1C0h+var_178], rax
0x1800115ed  lea     r9, byte_180147320
0x1800115f4  mov     [rsp+1C0h+var_180], rcx
0x1800115f9  lea     rax, [rbp+0C0h+var_138]
0x1800115fd  mov     [rsp+1C0h+var_188], rax
0x180011602  lea     rdx, PLA_EVENT_ALLOC
0x180011609  lea     rax, [rsp+1C0h+var_150]
0x18001160e  mov     [rsp+1C0h+var_190], r15
0x180011613  mov     [rsp+1C0h+var_198], rax
0x180011618  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18001161f  mov     [rsp+1C0h+var_1A0], r12
0x180011624  call    EventingWriteEvent
0x180011629  mov     rcx, cs:qword_180169748
0x180011630  mov     edx, dword ptr cs:xmmword_180169738
0x180011636  test    rdi, rdi
0x180011639  jnz     loc_180011708
0x18001163f  mov     [rsp+1C0h+var_150], r14d
0x180011644  mov     ebx, 8007000Eh
0x180011649  mov     dword ptr [rsp+1C0h+var_148], ebx
0x18001164d  test    edx, edx
0x18001164f  jz      loc_18001183D
0x180011655  mov     rdx, 4000000000000800h; unsigned __int64
0x18001165f  test    qword ptr cs:xmmword_180169738+8, rdx
0x180011666  jz      loc_18001183D
0x18001166c  mov     rax, rcx
0x18001166f  and     rax, rdx
0x180011672  cmp     rcx, rax
0x180011675  jnz     loc_18001183D
0x18001167b  lea     rcx, [rbp+0C0h+var_130]; unsigned __int16 *
0x18001167f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180011684  lea     rcx, [rbp+0C0h+var_130]
0x180011688  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001168c  inc     rax
0x18001168f  cmp     [rcx+rax*2], r14w
0x180011694  jnz     short loc_18001168C
0x180011696  lea     ecx, [rax+rax]
0x180011699  mov     r8d, 5
0x18001169f  add     rcx, 2
0x1800116a3  lea     rax, [rbp+0C0h+var_130]
0x1800116a7  mov     [rsp+1C0h+var_160], rcx
0x1800116ac  lea     r9, [rsp+1C0h+var_148]
0x1800116b1  mov     [rsp+1C0h+var_168], rax
0x1800116b6  lea     rdx, PLA_EVENT_ERROR
0x1800116bd  mov     [rsp+1C0h+var_170], 11h
0x1800116c6  lea     rax, aPlaiisadmintok; "PlaiIsAdminToken"
0x1800116cd  mov     [rsp+1C0h+var_178], rax
0x1800116d2  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800116d9  mov     [rsp+1C0h+var_180], r15
0x1800116de  lea     rax, [rsp+1C0h+var_150]
0x1800116e3  mov     [rsp+1C0h+var_188], rax
0x1800116e8  lea     rax, byte_180147320
0x1800116ef  mov     [rsp+1C0h+var_190], r12
0x1800116f4  mov     [rsp+1C0h+var_198], rax
0x1800116f9  mov     [rsp+1C0h+var_1A0], r15
0x1800116fe  call    EventingWriteEvent
0x180011703  jmp     loc_18001183D
0x180011708  xor     edx, edx; DomainSid
0x18001170a  lea     r9, [rbp+0C0h+cbSid]; cbSid
0x18001170e  mov     r8, rdi; pSid
0x180011711  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x180011714  call    cs:__imp_CreateWellKnownSid
0x18001171a  test    eax, eax
0x18001171c  jnz     loc_180011807
0x180011722  call    cs:__imp_GetLastError
0x180011728  mov     ecx, eax; unsigned int
0x18001172a  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18001172f  mov     ebx, eax
0x180011731  test    eax, eax
0x180011733  jns     loc_180011807
0x180011739  cmp     dword ptr cs:xmmword_180169738, r14d
0x180011740  mov     dword ptr [rsp+1C0h+var_148], r14d
0x180011745  mov     [rsp+1C0h+var_150], eax
0x180011749  jz      loc_180011832
0x18001174f  mov     rdx, 4000000000000800h; unsigned __int64
0x180011759  test    qword ptr cs:xmmword_180169738+8, rdx
0x180011760  jz      loc_180011832
0x180011766  mov     rax, cs:qword_180169748
0x18001176d  and     rax, rdx
0x180011770  cmp     cs:qword_180169748, rax
0x180011777  jnz     loc_180011832
0x18001177d  lea     rcx, [rbp+0C0h+var_B0]; unsigned __int16 *
0x180011781  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180011786  lea     rcx, [rbp+0C0h+var_B0]
0x18001178a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001178e  inc     rax
0x180011791  cmp     [rcx+rax*2], r14w
0x180011796  jnz     short loc_18001178E
0x180011798  lea     ecx, [rax+rax]
0x18001179b  mov     r8d, 5
0x1800117a1  add     rcx, 2
0x1800117a5  lea     rax, [rbp+0C0h+var_B0]
0x1800117a9  mov     [rsp+1C0h+var_160], rcx
0x1800117ae  lea     r9, [rsp+1C0h+var_150]
0x1800117b3  mov     [rsp+1C0h+var_168], rax
0x1800117b8  lea     rdx, PLA_EVENT_ERROR
0x1800117bf  mov     [rsp+1C0h+var_170], 11h
0x1800117c8  lea     rax, aPlaiisadmintok; "PlaiIsAdminToken"
0x1800117cf  mov     [rsp+1C0h+var_178], rax
0x1800117d4  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800117db  mov     [rsp+1C0h+var_180], r15
0x1800117e0  lea     rax, [rsp+1C0h+var_148]
0x1800117e5  mov     [rsp+1C0h+var_188], rax
0x1800117ea  lea     rax, byte_180147320
0x1800117f1  mov     [rsp+1C0h+var_190], r12
0x1800117f6  mov     [rsp+1C0h+var_198], rax
0x1800117fb  mov     [rsp+1C0h+var_1A0], r15
0x180011800  call    EventingWriteEvent
0x180011805  jmp     short loc_180011832
0x180011807  mov     r8, rsi; IsMember
0x18001180a  mov     rdx, rdi; SidToCheck
0x18001180d  xor     ecx, ecx; TokenHandle
0x18001180f  call    cs:__imp_CheckTokenMembership
0x180011815  test    eax, eax
0x180011817  jnz     short loc_18001182F
0x180011819  call    cs:__imp_GetLastError
0x18001181f  mov     ecx, eax; unsigned int
0x180011821  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180011826  mov     ebx, eax
0x180011828  test    eax, eax
0x18001182a  jns     short loc_180011832
0x18001182c  mov     [rsi], r14d
0x18001182f  mov     ebx, r14d
0x180011832  mov     edx, r12d; int
0x180011835  mov     rcx, rdi; lpMem
0x180011838  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x18001183d  mov     eax, ebx
0x18001183f  mov     rcx, [rbp+0C0h+var_30]
0x180011846  xor     rcx, rsp; StackCookie
0x180011849  call    __security_check_cookie
0x18001184e  lea     r11, [rsp+1C0h+var_20]
0x180011856  mov     rbx, [r11+38h]
0x18001185a  mov     rsi, [r11+40h]
0x18001185e  mov     rsp, r11
0x180011861  pop     r15
0x180011863  pop     r14
0x180011865  pop     r12
0x180011867  pop     rdi
0x180011868  pop     rbp
0x180011869  retn
```
