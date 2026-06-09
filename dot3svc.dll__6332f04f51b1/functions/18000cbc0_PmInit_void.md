# PmInit(void)

- ea: `0x18000cbc0`
- end: `0x18000cd24`
- name: `?PmInit@@YAKXZ`
- size: `356`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000aac0`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18000cbc0`
- `0x18001c080`
- `0x180032778`
- `0x18003386c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000cc07`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000cc07`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ccd8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ccd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc13`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000cc84`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000cc84`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000cce2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000cce2`

## pseudocode

```c
__int64 PmInit(void)
{
  int v0; // edi
  int v1; // esi
  DWORD ProfileSchemaCollection; // ebx
  HRESULT v3; // eax

  v0 = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 37, WPP_935883eb83d333df730e157613565e66_Traceguids);
  }
  if ( InitializeCriticalSectionAndSpinCount(&stru_180052D40, 0)
    || (v1 = 0, (ProfileSchemaCollection = GetLastError()) == 0) )
  {
    dword_180052D78 |= 0xFu;
    qword_180052D98 = (__int64)&qword_180052D90;
    qword_180052D90 = (__int64)&qword_180052D90;
    v1 = 1;
    qword_180052DD0 = (__int64)&qword_180052DC8;
    qword_180052DC8 = (__int64)&qword_180052DC8;
    dword_180052DB0 = dword_180052DB0 & 0xFFFFFFEE | 0x10;
    qword_180052DE0 = (__int64)&qword_180052DD8;
    qword_180052DD8 = (struct _PM_PCB_LIST *)&qword_180052DD8;
    v3 = CoInitializeEx(0, 0);
    ProfileSchemaCollection = v3;
    if ( v3 >= 0 )
      goto LABEL_11;
    if ( (v3 & 0x1FFF0000) == 0x70000 )
      ProfileSchemaCollection = (unsigned __int16)v3;
    if ( !ProfileSchemaCollection )
    {
LABEL_11:
      ProfileSchemaCollection = LpCreateProfileSchemaCollection(&qword_180052CD8);
      if ( !ProfileSchemaCollection )
      {
        InitializeForPLAP();
LABEL_19:
        CoUninitialize();
        goto LABEL_20;
      }
      v0 = 1;
    }
  }
  if ( qword_180052CD8 )
    LpReleaseProfileSchemaCollection();
  if ( v1 )
    DeleteCriticalSection(&stru_180052D40);
  if ( v0 )
    goto LABEL_19;
LABEL_20:
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 38, WPP_935883eb83d333df730e157613565e66_Traceguids, ProfileSchemaCollection);
  }
  return ProfileSchemaCollection;
}

```

## disassembly

```asm
0x18000cbc0  push    rbx
0x18000cbc2  push    rsi
0x18000cbc3  push    rdi
0x18000cbc4  push    r14
0x18000cbc6  sub     rsp, 28h
0x18000cbca  xor     edi, edi
0x18000cbcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cbd3  lea     r14, WPP_GLOBAL_Control
0x18000cbda  cmp     rcx, r14
0x18000cbdd  jz      short loc_18000CBFE
0x18000cbdf  cmp     byte ptr [rcx+19h], 4
0x18000cbe3  jb      short loc_18000CBFE
0x18000cbe5  test    byte ptr [rcx+1Ch], 1
0x18000cbe9  jz      short loc_18000CBFE
0x18000cbeb  mov     rcx, [rcx+10h]
0x18000cbef  lea     edx, [rdi+25h]
0x18000cbf2  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000cbf9  call    WPP_SF_
0x18000cbfe  xor     edx, edx; dwSpinCount
0x18000cc00  lea     rcx, stru_180052D40; lpCriticalSection
0x18000cc07  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000cc0d  test    eax, eax
0x18000cc0f  jnz     short loc_18000CC23
0x18000cc11  xor     esi, esi
0x18000cc13  call    cs:__imp_GetLastError
0x18000cc19  mov     ebx, eax
0x18000cc1b  test    eax, eax
0x18000cc1d  jnz     loc_18000CCBE
0x18000cc23  or      cs:dword_180052D78, 0Fh
0x18000cc2a  lea     rax, qword_180052D90
0x18000cc31  mov     cs:qword_180052D98, rax
0x18000cc38  xor     edx, edx; dwCoInit
0x18000cc3a  mov     cs:qword_180052D90, rax
0x18000cc41  xor     ecx, ecx; pvReserved
0x18000cc43  lea     rax, qword_180052DC8
0x18000cc4a  mov     esi, 1
0x18000cc4f  mov     cs:qword_180052DD0, rax
0x18000cc56  mov     cs:qword_180052DC8, rax
0x18000cc5d  mov     eax, cs:dword_180052DB0
0x18000cc63  and     eax, 0FFFFFFFEh
0x18000cc66  or      eax, 10h
0x18000cc69  mov     cs:dword_180052DB0, eax
0x18000cc6f  lea     rax, qword_180052DD8
0x18000cc76  mov     cs:qword_180052DE0, rax
0x18000cc7d  mov     cs:qword_180052DD8, rax
0x18000cc84  call    cs:__imp_CoInitializeEx
0x18000cc8a  mov     ebx, eax
0x18000cc8c  test    eax, eax
0x18000cc8e  jns     short loc_18000CCA3
0x18000cc90  and     eax, 1FFF0000h
0x18000cc95  cmp     eax, 70000h
0x18000cc9a  jnz     short loc_18000CC9F
0x18000cc9c  movzx   ebx, bx
0x18000cc9f  test    ebx, ebx
0x18000cca1  jnz     short loc_18000CCBE
0x18000cca3  lea     rcx, qword_180052CD8
0x18000ccaa  call    LpCreateProfileSchemaCollection
0x18000ccaf  mov     ebx, eax
0x18000ccb1  test    eax, eax
0x18000ccb3  jnz     short loc_18000CCBC
0x18000ccb5  call    ?InitializeForPLAP@@YAKXZ; InitializeForPLAP(void)
0x18000ccba  jmp     short loc_18000CCE2
0x18000ccbc  mov     edi, esi
0x18000ccbe  cmp     cs:qword_180052CD8, 0
0x18000ccc6  jz      short loc_18000CCCD
0x18000ccc8  call    LpReleaseProfileSchemaCollection
0x18000cccd  test    esi, esi
0x18000cccf  jz      short loc_18000CCDE
0x18000ccd1  lea     rcx, stru_180052D40; lpCriticalSection
0x18000ccd8  call    cs:__imp_DeleteCriticalSection
0x18000ccde  test    edi, edi
0x18000cce0  jz      short loc_18000CCE8
0x18000cce2  call    cs:__imp_CoUninitialize
0x18000cce8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccef  cmp     rcx, r14
0x18000ccf2  jz      short loc_18000CD18
0x18000ccf4  cmp     byte ptr [rcx+19h], 4
0x18000ccf8  jb      short loc_18000CD18
0x18000ccfa  test    byte ptr [rcx+1Ch], 1
0x18000ccfe  jz      short loc_18000CD18
0x18000cd00  mov     rcx, [rcx+10h]
0x18000cd04  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000cd0b  mov     edx, 26h ; '&'
0x18000cd10  mov     r9d, ebx
0x18000cd13  call    WPP_SF_d
0x18000cd18  mov     eax, ebx
0x18000cd1a  add     rsp, 28h
0x18000cd1e  pop     r14
0x18000cd20  pop     rdi
0x18000cd21  pop     rsi
0x18000cd22  pop     rbx
0x18000cd23  retn
```
