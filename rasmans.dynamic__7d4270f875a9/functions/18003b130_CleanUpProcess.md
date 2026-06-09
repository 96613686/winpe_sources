# CleanUpProcess

- ea: `0x18003b130`
- end: `0x18003b5e1`
- name: `CleanUpProcess`
- size: `1201`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x180029300`
- `0x180038db0`
- `0x18003accc`
- `0x18004946c`

## callees

- `0x180005a20`
- `0x180005bcc`
- `0x180005bfc`
- `0x18000c37c`
- `0x18003372c`
- `0x1800391a4`
- `0x18003af28`
- `0x18003b130`
- `0x180040a7c`
- `0x18004bcd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b30c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b30c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b283`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b283`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b1a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b3a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b1a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b3a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b230`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b389`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b559`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e95f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b230`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b389`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b559`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e95f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b2a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b36f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b4ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b2a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b36f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b4ac`

## pseudocode

```c
__int64 __fastcall CleanUpProcess(unsigned int a1)
{
  unsigned int v1; // r12d
  unsigned int v2; // esi
  HANDLE *v3; // rbx
  __int64 i; // rax
  struct _LIST_ENTRY *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  struct _LIST_ENTRY *v8; // rcx
  _QWORD *v9; // rdx
  HANDLE *v10; // rax
  unsigned int v11; // eax
  struct _LIST_ENTRY *v12; // rcx
  DWORD CurrentProcessId; // eax
  __int64 v14; // r9
  HLOCAL v15; // r9
  _QWORD *v16; // r15
  HANDLE *v17; // rbx
  HANDLE *v18; // r12

  v1 = a1;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 )
  {
    v2 = 1;
  }
  else
  {
    v2 = 1;
    if ( BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      WPP_SF_dc(WPP_GLOBAL_Control[1].Flink, 111, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, a1, 1);
  }
  v3 = 0;
  EnterCriticalSection(&g_csClientProcessBlock);
  for ( i = ClientProcessBlockList; ; i = *(_QWORD *)i )
  {
    if ( (__int64 *)i == &ClientProcessBlockList )
      goto LABEL_21;
    if ( !i )
      break;
    if ( *(_DWORD *)(i + 24) == v1 )
    {
      v3 = (HANDLE *)i;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        v6 = 114;
LABEL_20:
        WPP_SF_(v5[1].Flink, v6, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
        goto LABEL_21;
      }
      goto LABEL_21;
    }
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
  {
    v6 = 112;
    goto LABEL_20;
  }
LABEL_21:
  if ( !v3 )
  {
    LeaveCriticalSection(&g_csClientProcessBlock);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 115, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v1);
      v8 = WPP_GLOBAL_Control;
    }
    v2 = 0;
    goto LABEL_56;
  }
  CloseHandle(v3[2]);
  CleanUpEventQueue(v3 + 4);
  v9 = *v3;
  v10 = (HANDLE *)v3[1];
  *v10 = *v3;
  v9[1] = v10;
  LocalFree(v3);
  v11 = g_dwAttachedCount;
  if ( g_dwAttachedCount )
    v11 = --g_dwAttachedCount;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 116, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v11);
    v12 = WPP_GLOBAL_Control;
    v11 = g_dwAttachedCount;
  }
  if ( !v11 )
    goto LABEL_37;
  if ( v11 == 1 )
  {
    CurrentProcessId = GetCurrentProcessId();
    if ( FindProcess(CurrentProcessId) )
    {
      v12 = WPP_GLOBAL_Control;
LABEL_37:
      v14 = g_pDeadClientTimeoutElement;
      if ( g_pDeadClientTimeoutElement )
      {
        if ( v12 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v12[1].Blink) & 0x2000) != 0
          && BYTE1(v12[1].Blink) >= 5u )
        {
          WPP_SF_(v12[1].Flink, 117, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
          v14 = g_pDeadClientTimeoutElement;
        }
        DequeueTimeoutElement(v14);
        LocalFree(v15);
        g_pDeadClientTimeoutElement = 0;
      }
    }
  }
  LeaveCriticalSection(&g_csClientProcessBlock);
  EnterCriticalSection(&g_csConnectionNotifierList);
  v16 = pConnectionNotifierList;
  v17 = (HANDLE *)pConnectionNotifierList;
  while ( v17 )
  {
    if ( *((_DWORD *)v17 + 5) == v1 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 118, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v1);
      }
      FreeNotifierHandle(v17[1]);
      v17[1] = (HANDLE)-1LL;
      v18 = (HANDLE *)*v17;
      if ( v17 == pConnectionNotifierList )
      {
        v16 = *v17;
        pConnectionNotifierList = *v17;
      }
      else
      {
        *v16 = v18;
      }
      LocalFree(v17);
      v17 = v18;
      v1 = a1;
    }
    else
    {
      v16 = v17;
      v17 = (HANDLE *)*v17;
    }
  }
  LeaveCriticalSection(&g_csConnectionNotifierList);
  v8 = WPP_GLOBAL_Control;
LABEL_56:
  if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v8[1].Blink) & 0x2000) != 0
    && BYTE1(v8[1].Blink) >= 6u )
  {
    LOBYTE(v7) = v2;
    WPP_SF_c(v8[1].Flink, 122, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v7);
  }
  return v2;
}

```

## disassembly

```asm
0x18003b130  mov     rax, rsp
0x18003b133  mov     [rax+18h], rbx
0x18003b137  mov     [rax+20h], rsi
0x18003b13b  mov     [rax+10h], edx
0x18003b13e  mov     [rax+8], ecx
0x18003b141  push    rdi
0x18003b142  push    r12
0x18003b144  push    r13
0x18003b146  push    r14
0x18003b148  push    r15
0x18003b14a  sub     rsp, 50h
0x18003b14e  mov     r12d, ecx
0x18003b151  lea     r13, WPP_GLOBAL_Control
0x18003b158  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b15f  mov     r14d, 2000h
0x18003b165  cmp     rcx, r13
0x18003b168  jz      short loc_18003B197
0x18003b16a  test    [rcx+1Ch], r14d
0x18003b16e  jz      short loc_18003B197
0x18003b170  mov     esi, 1
0x18003b175  cmp     byte ptr [rcx+19h], 6
0x18003b179  jb      short loc_18003B19C
0x18003b17b  lea     edx, [rsi+6Eh]
0x18003b17e  mov     [rax-58h], sil
0x18003b182  mov     r9d, r12d
0x18003b185  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003b18c  mov     rcx, [rcx+10h]
0x18003b190  call    WPP_SF_dc
0x18003b195  jmp     short loc_18003B19C
0x18003b197  mov     esi, 1
0x18003b19c  xor     ebx, ebx
0x18003b19e  lea     rdi, g_csClientProcessBlock
0x18003b1a5  mov     rcx, rdi; lpCriticalSection
0x18003b1a8  call    cs:__imp_EnterCriticalSection
0x18003b1af  nop     dword ptr [rax+rax+00h]
0x18003b1b4  mov     rax, cs:ClientProcessBlockList
0x18003b1bb  lea     rcx, ClientProcessBlockList
0x18003b1c2  jmp     short loc_18003B1D2
0x18003b1c4  test    rax, rax
0x18003b1c7  jz      short loc_18003B1FB
0x18003b1c9  cmp     [rax+18h], r12d
0x18003b1cd  jz      short loc_18003B1D9
0x18003b1cf  mov     rax, [rax]
0x18003b1d2  cmp     rax, rcx
0x18003b1d5  jnz     short loc_18003B1C4
0x18003b1d7  jmp     short loc_18003B228
0x18003b1d9  mov     rbx, rax
0x18003b1dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b1e3  cmp     rcx, r13
0x18003b1e6  jz      short loc_18003B228
0x18003b1e8  test    [rcx+1Ch], r14d
0x18003b1ec  jz      short loc_18003B228
0x18003b1ee  cmp     byte ptr [rcx+19h], 5
0x18003b1f2  jb      short loc_18003B228
0x18003b1f4  mov     edx, 72h ; 'r'
0x18003b1f9  jmp     short loc_18003B218
0x18003b1fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b202  cmp     rcx, r13
0x18003b205  jz      short loc_18003B228
0x18003b207  test    [rcx+1Ch], r14d
0x18003b20b  jz      short loc_18003B228
0x18003b20d  cmp     byte ptr [rcx+19h], 5
0x18003b211  jb      short loc_18003B228
0x18003b213  mov     edx, 70h ; 'p'
0x18003b218  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003b21f  mov     rcx, [rcx+10h]
0x18003b223  call    WPP_SF_
0x18003b228  test    rbx, rbx
0x18003b22b  jnz     short loc_18003B278
0x18003b22d  mov     rcx, rdi; lpCriticalSection
0x18003b230  call    cs:__imp_LeaveCriticalSection
0x18003b237  nop     dword ptr [rax+rax+00h]
0x18003b23c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b243  cmp     rcx, r13
0x18003b246  jz      short loc_18003B271
0x18003b248  test    [rcx+1Ch], r14d
0x18003b24c  jz      short loc_18003B271
0x18003b24e  cmp     byte ptr [rcx+19h], 5
0x18003b252  jb      short loc_18003B271
0x18003b254  lea     edx, [rbx+73h]
0x18003b257  mov     r9d, r12d
0x18003b25a  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003b261  mov     rcx, [rcx+10h]
0x18003b265  call    WPP_SF_d
0x18003b26a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b271  xor     esi, esi
0x18003b273  jmp     loc_18003B59B
0x18003b278  mov     [rsp+78h+arg_8], esi
0x18003b27f  mov     rcx, [rbx+10h]; hObject
0x18003b283  call    cs:__imp_CloseHandle
0x18003b28a  nop     dword ptr [rax+rax+00h]
0x18003b28f  lea     rcx, [rbx+20h]
0x18003b293  call    CleanUpEventQueue
0x18003b298  mov     rdx, [rbx]
0x18003b29b  mov     rax, [rbx+8]
0x18003b29f  mov     [rax], rdx
0x18003b2a2  mov     [rdx+8], rax
0x18003b2a6  mov     rcx, rbx; hMem
0x18003b2a9  call    cs:__imp_LocalFree
0x18003b2b0  nop     dword ptr [rax+rax+00h]
0x18003b2b5  mov     eax, cs:g_dwAttachedCount
0x18003b2bb  test    eax, eax
0x18003b2bd  jz      short loc_18003B2C7
0x18003b2bf  dec     eax
0x18003b2c1  mov     cs:g_dwAttachedCount, eax
0x18003b2c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b2ce  cmp     rcx, r13
0x18003b2d1  jz      short loc_18003B304
0x18003b2d3  test    [rcx+1Ch], r14d
0x18003b2d7  jz      short loc_18003B304
0x18003b2d9  cmp     byte ptr [rcx+19h], 4
0x18003b2dd  jb      short loc_18003B304
0x18003b2df  mov     edx, 74h ; 't'
0x18003b2e4  mov     r9d, eax
0x18003b2e7  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003b2ee  mov     rcx, [rcx+10h]
0x18003b2f2  call    WPP_SF_d
0x18003b2f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b2fe  mov     eax, cs:g_dwAttachedCount
0x18003b304  test    eax, eax
0x18003b306  jz      short loc_18003B32B
0x18003b308  cmp     eax, esi
0x18003b30a  jnz     short loc_18003B386
0x18003b30c  call    cs:__imp_GetCurrentProcessId
0x18003b313  nop     dword ptr [rax+rax+00h]
0x18003b318  mov     ecx, eax
0x18003b31a  call    FindProcess
0x18003b31f  test    rax, rax
0x18003b322  jz      short loc_18003B386
0x18003b324  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b32b  mov     r9, cs:g_pDeadClientTimeoutElement
0x18003b332  test    r9, r9
0x18003b335  jz      short loc_18003B386
0x18003b337  cmp     rcx, r13
0x18003b33a  jz      short loc_18003B364
0x18003b33c  test    [rcx+1Ch], r14d
0x18003b340  jz      short loc_18003B364
0x18003b342  cmp     byte ptr [rcx+19h], 5
0x18003b346  jb      short loc_18003B364
0x18003b348  mov     edx, 75h ; 'u'
0x18003b34d  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003b354  mov     rcx, [rcx+10h]
0x18003b358  call    WPP_SF_
0x18003b35d  mov     r9, cs:g_pDeadClientTimeoutElement
0x18003b364  mov     rcx, r9
0x18003b367  call    DequeueTimeoutElement
0x18003b36c  mov     rcx, r9; hMem
0x18003b36f  call    cs:__imp_LocalFree
0x18003b376  nop     dword ptr [rax+rax+00h]
0x18003b37b  mov     cs:g_pDeadClientTimeoutElement, 0
0x18003b386  mov     rcx, rdi; lpCriticalSection
0x18003b389  call    cs:__imp_LeaveCriticalSection
0x18003b390  nop     dword ptr [rax+rax+00h]
0x18003b395  xor     edi, edi
0x18003b397  mov     [rsp+78h+var_44], edi
0x18003b39b  mov     [rsp+78h+var_48], edi
0x18003b39f  lea     rcx, g_csConnectionNotifierList; lpCriticalSection
0x18003b3a6  call    cs:__imp_EnterCriticalSection
0x18003b3ad  nop     dword ptr [rax+rax+00h]
0x18003b3b2  mov     [rsp+78h+var_48], esi
0x18003b3b6  mov     r15, cs:pConnectionNotifierList
0x18003b3bd  mov     [rsp+78h+var_38], r15
0x18003b3c2  mov     rbx, r15
0x18003b3c5  mov     [rsp+78h+var_40], rbx
0x18003b3ca  test    rbx, rbx
0x18003b3cd  jz      loc_18003B4E3
0x18003b3d3  cmp     [rbx+14h], r12d
0x18003b3d7  jnz     loc_18003B4CE
0x18003b3dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b3e4  cmp     rcx, r13
0x18003b3e7  jz      short loc_18003B40E
0x18003b3e9  test    [rcx+1Ch], r14d
0x18003b3ed  jz      short loc_18003B40E
0x18003b3ef  cmp     byte ptr [rcx+19h], 5
0x18003b3f3  jb      short loc_18003B40E
0x18003b3f5  mov     edx, 76h ; 'v'
0x18003b3fa  mov     r9d, r12d
0x18003b3fd  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003b404  mov     rcx, [rcx+10h]
0x18003b408  call    WPP_SF_d
0x18003b40d  nop
0x18003b40e  mov     rcx, [rbx+8]; hObject
0x18003b412  call    FreeNotifierHandle
0x18003b417  jmp     short loc_18003B481
0x18003b419  lea     rdx, WPP_GLOBAL_Control
0x18003b420  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b427  cmp     rcx, rdx
0x18003b42a  jz      short loc_18003B45F
0x18003b42c  test    dword ptr [rcx+1Ch], 2000h
0x18003b433  jz      short loc_18003B45F
0x18003b435  cmp     byte ptr [rcx+19h], 2
0x18003b439  jb      short loc_18003B45F
0x18003b43b  mov     edx, 77h ; 'w'
0x18003b440  mov     [rsp+78h+var_58], eax
0x18003b444  mov     rbx, [rsp+78h+var_40]
0x18003b449  mov     r9, [rbx+8]
0x18003b44d  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003b454  mov     rcx, [rcx+10h]
0x18003b458  call    WPP_SF_qD
0x18003b45d  jmp     short loc_18003B464
0x18003b45f  mov     rbx, [rsp+78h+var_40]
0x18003b464  lea     r13, WPP_GLOBAL_Control
0x18003b46b  mov     r14d, 2000h
0x18003b471  mov     esi, [rsp+78h+arg_8]
0x18003b478  mov     r15, [rsp+78h+var_38]
0x18003b47d  mov     edi, [rsp+78h+var_44]
0x18003b481  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x18003b489  mov     r12, [rbx]
0x18003b48c  cmp     rbx, cs:pConnectionNotifierList
0x18003b493  jnz     short loc_18003B4A6
0x18003b495  mov     r15, r12
0x18003b498  mov     [rsp+78h+var_38], r12
0x18003b49d  mov     cs:pConnectionNotifierList, r12
0x18003b4a4  jmp     short loc_18003B4A9
0x18003b4a6  mov     [r15], r12
0x18003b4a9  mov     rcx, rbx; hMem
0x18003b4ac  call    cs:__imp_LocalFree
0x18003b4b3  nop     dword ptr [rax+rax+00h]
0x18003b4b8  mov     [rsp+78h+var_40], 0
0x18003b4c1  mov     rbx, r12
0x18003b4c4  mov     r12d, [rsp+78h+arg_0]
0x18003b4cc  jmp     short loc_18003B4D9
0x18003b4ce  mov     r15, rbx
0x18003b4d1  mov     [rsp+78h+var_38], rbx
0x18003b4d6  mov     rbx, [rbx]
0x18003b4d9  mov     [rsp+78h+var_40], rbx
0x18003b4de  jmp     loc_18003B3CA
0x18003b4e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b4ea  jmp     short loc_18003B54B
0x18003b4ec  mov     edi, eax
0x18003b4ee  mov     [rsp+78h+var_44], eax
0x18003b4f2  test    eax, eax
0x18003b4f4  jz      short loc_18003B530
0x18003b4f6  lea     rax, WPP_GLOBAL_Control
0x18003b4fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b504  cmp     rcx, rax
0x18003b507  jz      short loc_18003B537
0x18003b509  test    dword ptr [rcx+1Ch], 2000h
0x18003b510  jz      short loc_18003B537
0x18003b512  cmp     byte ptr [rcx+19h], 2
0x18003b516  jb      short loc_18003B537
0x18003b518  mov     edx, 78h ; 'x'
0x18003b51d  mov     r9d, edi
0x18003b520  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003b527  mov     rcx, [rcx+10h]
0x18003b52b  call    WPP_SF_d
0x18003b530  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b537  lea     r13, WPP_GLOBAL_Control
0x18003b53e  mov     r14d, 2000h
0x18003b544  mov     esi, [rsp+78h+arg_8]
0x18003b54b  cmp     [rsp+78h+var_48], 0
0x18003b550  jz      short loc_18003B567
0x18003b552  lea     rcx, g_csConnectionNotifierList; lpCriticalSection
0x18003b559  call    cs:__imp_LeaveCriticalSection
0x18003b560  nop     dword ptr [rax+rax+00h]
0x18003b565  jmp     short loc_18003B594
0x18003b567  test    edi, edi
0x18003b569  jz      short loc_18003B59B
0x18003b56b  cmp     rcx, r13
0x18003b56e  jz      short loc_18003B5C4
0x18003b570  test    [rcx+1Ch], r14d
0x18003b574  jz      short loc_18003B59B
0x18003b576  cmp     byte ptr [rcx+19h], 2
0x18003b57a  jb      short loc_18003B59B
0x18003b57c  mov     edx, 79h ; 'y'
0x18003b581  mov     r9d, edi
0x18003b584  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003b58b  mov     rcx, [rcx+10h]
0x18003b58f  call    WPP_SF_d
0x18003b594  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b59b  cmp     rcx, r13
0x18003b59e  jz      short loc_18003B5C4
0x18003b5a0  test    [rcx+1Ch], r14d
0x18003b5a4  jz      short loc_18003B5C4
0x18003b5a6  cmp     byte ptr [rcx+19h], 6
0x18003b5aa  jb      short loc_18003B5C4
0x18003b5ac  mov     r9b, sil
0x18003b5af  mov     edx, 7Ah ; 'z'
0x18003b5b4  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18003b5bb  mov     rcx, [rcx+10h]
0x18003b5bf  call    WPP_SF_c
0x18003b5c4  mov     eax, esi
0x18003b5c6  lea     r11, [rsp+78h+var_28]
0x18003b5cb  mov     rbx, [r11+40h]
0x18003b5cf  mov     rsi, [r11+48h]
0x18003b5d3  mov     rsp, r11
0x18003b5d6  pop     r15
0x18003b5d8  pop     r14
0x18003b5da  pop     r13
0x18003b5dc  pop     r12
0x18003b5de  pop     rdi
0x18003b5df  retn
0x1800e95e1  push    rbp
0x1800e95e3  sub     rsp, 30h
0x1800e95e7  mov     rbp, rdx
0x1800e95ea  cmp     dword ptr [rbp+30h], 0
0x1800e95ee  jz      short loc_1800E9605
0x1800e95f0  lea     rcx, g_csConnectionNotifierList; lpCriticalSection
0x1800e95f7  call    cs:__imp_LeaveCriticalSection
0x1800e95fe  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
