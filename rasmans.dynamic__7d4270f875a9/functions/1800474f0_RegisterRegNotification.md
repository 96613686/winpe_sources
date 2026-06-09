# RegisterRegNotification

- ea: `0x1800474f0`
- end: `0x1800477b6`
- name: `RegisterRegNotification`
- size: `710`
- prototype: `__int64 __fastcall(PHKEY phkResult, PHKEY)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800429b0`
- `0x1800463fc`

## callees

- `0x180005bfc`
- `0x18000c37c`
- `0x1800474f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800475af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800475af`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180047588`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18004759f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180047588`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18004759f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004760e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180047669`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004760e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180047669`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800476c0`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18004773e`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800476c0`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18004773e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004754f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004756a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004754f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004756a`

## string_xrefs

- `0x18004765b`: `System\CurrentControlSet\Services\LanmanWorkstation\Linkage`
- `0x180047600`: `System\CurrentControlSet\Services\LanmanServer\Linkage`

## pseudocode

```c
__int64 __fastcall RegisterRegNotification(PHKEY phkResult, PHKEY a2, int a3, __int64 a4)
{
  DWORD LastError; // eax
  DWORD v8; // ebx
  struct _LIST_ENTRY *v9; // rcx
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // r9

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    LOBYTE(a4) = a3 != 0;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 687, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, a4);
  }
  if ( *phkResult )
  {
    RegCloseKey(*phkResult);
    *phkResult = 0;
  }
  if ( *a2 )
  {
    RegCloseKey(*a2);
    *phkResult = 0;
  }
  if ( a3 && (!ResetEvent(hEvent) || !ResetEvent(qword_180110DB0)) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v8;
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_44;
      v10 = 688;
LABEL_41:
      v12 = LastError;
LABEL_42:
      WPP_SF_d(v9[1].Flink, v10, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v12);
    }
LABEL_43:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_44;
  }
  LastError = RegOpenKeyExA(
                HKEY_LOCAL_MACHINE,
                "System\\CurrentControlSet\\Services\\LanmanServer\\Linkage",
                0,
                0x10u,
                phkResult);
  v8 = LastError;
  if ( LastError )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return v8;
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_44;
    v10 = 689;
    goto LABEL_41;
  }
  LastError = RegOpenKeyExA(
                HKEY_LOCAL_MACHINE,
                "System\\CurrentControlSet\\Services\\LanmanWorkstation\\Linkage",
                0,
                0x10u,
                a2);
  v8 = LastError;
  if ( LastError )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return v8;
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_44;
    v10 = 690;
    goto LABEL_41;
  }
  v11 = RegNotifyChangeKeyValue(*phkResult, 0, 4u, hEvent, 1);
  v8 = v11;
  if ( !v11 )
  {
    LastError = RegNotifyChangeKeyValue(*a2, 0, 4u, qword_180110DB0, 1);
    v8 = LastError;
    if ( LastError )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v8;
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_44;
      v10 = 693;
      goto LABEL_41;
    }
    goto LABEL_43;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 691, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v11);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(v9[1].Blink) & 0x2000) == 0 || BYTE1(v9[1].Blink) < 2u )
      {
LABEL_44:
        if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v9[1].Blink) & 0x2000) != 0
          && BYTE1(v9[1].Blink) >= 6u )
        {
          WPP_SF_d(v9[1].Flink, 694, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v8);
        }
        return v8;
      }
      v10 = 692;
      v12 = v8;
      goto LABEL_42;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800474f0  push    rbx
0x1800474f2  push    rbp
0x1800474f3  push    rsi
0x1800474f4  push    rdi
0x1800474f5  push    r14
0x1800474f7  push    r15
0x1800474f9  sub     rsp, 38h
0x1800474fd  mov     ebx, r8d
0x180047500  mov     rsi, rdx
0x180047503  mov     rdi, rcx
0x180047506  mov     rcx, cs:WPP_GLOBAL_Control
0x18004750d  lea     r14, WPP_GLOBAL_Control
0x180047514  lea     r15, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18004751b  mov     ebp, 2000h
0x180047520  cmp     rcx, r14
0x180047523  jz      short loc_180047547
0x180047525  test    [rcx+1Ch], ebp
0x180047528  jz      short loc_180047547
0x18004752a  cmp     byte ptr [rcx+19h], 6
0x18004752e  jb      short loc_180047547
0x180047530  mov     rcx, [rcx+10h]
0x180047534  test    ebx, ebx
0x180047536  mov     edx, 2AFh
0x18004753b  mov     r8, r15
0x18004753e  setnz   r9b
0x180047542  call    WPP_SF_c
0x180047547  mov     rcx, [rdi]; hKey
0x18004754a  test    rcx, rcx
0x18004754d  jz      short loc_180047562
0x18004754f  call    cs:__imp_RegCloseKey
0x180047556  nop     dword ptr [rax+rax+00h]
0x18004755b  mov     qword ptr [rdi], 0
0x180047562  mov     rcx, [rsi]; hKey
0x180047565  test    rcx, rcx
0x180047568  jz      short loc_18004757D
0x18004756a  call    cs:__imp_RegCloseKey
0x180047571  nop     dword ptr [rax+rax+00h]
0x180047576  mov     qword ptr [rdi], 0
0x18004757d  test    ebx, ebx
0x18004757f  jz      short loc_1800475F2
0x180047581  mov     rcx, cs:hEvent; hEvent
0x180047588  call    cs:__imp_ResetEvent
0x18004758f  nop     dword ptr [rax+rax+00h]
0x180047594  test    eax, eax
0x180047596  jz      short loc_1800475AF
0x180047598  mov     rcx, cs:qword_180110DB0; hEvent
0x18004759f  call    cs:__imp_ResetEvent
0x1800475a6  nop     dword ptr [rax+rax+00h]
0x1800475ab  test    eax, eax
0x1800475ad  jnz     short loc_1800475F2
0x1800475af  call    cs:__imp_GetLastError
0x1800475b6  nop     dword ptr [rax+rax+00h]
0x1800475bb  mov     ebx, eax
0x1800475bd  test    eax, eax
0x1800475bf  jz      loc_18004777B
0x1800475c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800475cc  cmp     rcx, r14
0x1800475cf  jz      loc_1800477A6
0x1800475d5  test    [rcx+1Ch], ebp
0x1800475d8  jz      loc_180047782
0x1800475de  cmp     byte ptr [rcx+19h], 2
0x1800475e2  jb      loc_180047782
0x1800475e8  mov     edx, 2B0h
0x1800475ed  jmp     loc_18004776C
0x1800475f2  mov     r9d, 10h; samDesired
0x1800475f8  mov     [rsp+68h+phkResult], rdi; phkResult
0x1800475fd  xor     r8d, r8d; ulOptions
0x180047600  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\La"...
0x180047607  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004760e  call    cs:__imp_RegOpenKeyExA
0x180047615  nop     dword ptr [rax+rax+00h]
0x18004761a  mov     ebx, eax
0x18004761c  test    eax, eax
0x18004761e  jz      short loc_18004764D
0x180047620  mov     rcx, cs:WPP_GLOBAL_Control
0x180047627  cmp     rcx, r14
0x18004762a  jz      loc_1800477A6
0x180047630  test    [rcx+1Ch], ebp
0x180047633  jz      loc_180047782
0x180047639  cmp     byte ptr [rcx+19h], 2
0x18004763d  jb      loc_180047782
0x180047643  mov     edx, 2B1h
0x180047648  jmp     loc_18004776C
0x18004764d  mov     r9d, 10h; samDesired
0x180047653  mov     [rsp+68h+phkResult], rsi; phkResult
0x180047658  xor     r8d, r8d; ulOptions
0x18004765b  lea     rdx, aSystemCurrentc_18; "System\\CurrentControlSet\\Services\\La"...
0x180047662  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180047669  call    cs:__imp_RegOpenKeyExA
0x180047670  nop     dword ptr [rax+rax+00h]
0x180047675  mov     ebx, eax
0x180047677  test    eax, eax
0x180047679  jz      short loc_1800476A8
0x18004767b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047682  cmp     rcx, r14
0x180047685  jz      loc_1800477A6
0x18004768b  test    [rcx+1Ch], ebp
0x18004768e  jz      loc_180047782
0x180047694  cmp     byte ptr [rcx+19h], 2
0x180047698  jb      loc_180047782
0x18004769e  mov     edx, 2B2h
0x1800476a3  jmp     loc_18004776C
0x1800476a8  mov     r9, cs:hEvent; hEvent
0x1800476af  xor     edx, edx; bWatchSubtree
0x1800476b1  mov     rcx, [rdi]; hKey
0x1800476b4  mov     dword ptr [rsp+68h+phkResult], 1; fAsynchronous
0x1800476bc  lea     r8d, [rdx+4]; dwNotifyFilter
0x1800476c0  call    cs:__imp_RegNotifyChangeKeyValue
0x1800476c7  nop     dword ptr [rax+rax+00h]
0x1800476cc  mov     ebx, eax
0x1800476ce  test    eax, eax
0x1800476d0  jz      short loc_180047726
0x1800476d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800476d9  cmp     rcx, r14
0x1800476dc  jz      loc_1800477A6
0x1800476e2  test    [rcx+1Ch], ebp
0x1800476e5  jz      short loc_180047708
0x1800476e7  cmp     byte ptr [rcx+19h], 2
0x1800476eb  jb      short loc_180047708
0x1800476ed  mov     rcx, [rcx+10h]
0x1800476f1  mov     edx, 2B3h
0x1800476f6  mov     r9d, eax
0x1800476f9  mov     r8, r15
0x1800476fc  call    WPP_SF_d
0x180047701  mov     rcx, cs:WPP_GLOBAL_Control
0x180047708  cmp     rcx, r14
0x18004770b  jz      loc_1800477A6
0x180047711  test    [rcx+1Ch], ebp
0x180047714  jz      short loc_180047782
0x180047716  cmp     byte ptr [rcx+19h], 2
0x18004771a  jb      short loc_180047782
0x18004771c  mov     edx, 2B4h
0x180047721  mov     r9d, ebx
0x180047724  jmp     short loc_18004776F
0x180047726  mov     r9, cs:qword_180110DB0; hEvent
0x18004772d  xor     edx, edx; bWatchSubtree
0x18004772f  mov     rcx, [rsi]; hKey
0x180047732  mov     dword ptr [rsp+68h+phkResult], 1; fAsynchronous
0x18004773a  lea     r8d, [rdx+4]; dwNotifyFilter
0x18004773e  call    cs:__imp_RegNotifyChangeKeyValue
0x180047745  nop     dword ptr [rax+rax+00h]
0x18004774a  mov     ebx, eax
0x18004774c  test    eax, eax
0x18004774e  jz      short loc_18004777B
0x180047750  mov     rcx, cs:WPP_GLOBAL_Control
0x180047757  cmp     rcx, r14
0x18004775a  jz      short loc_1800477A6
0x18004775c  test    [rcx+1Ch], ebp
0x18004775f  jz      short loc_180047782
0x180047761  cmp     byte ptr [rcx+19h], 2
0x180047765  jb      short loc_180047782
0x180047767  mov     edx, 2B5h
0x18004776c  mov     r9d, eax
0x18004776f  mov     rcx, [rcx+10h]
0x180047773  mov     r8, r15
0x180047776  call    WPP_SF_d
0x18004777b  mov     rcx, cs:WPP_GLOBAL_Control
0x180047782  cmp     rcx, r14
0x180047785  jz      short loc_1800477A6
0x180047787  test    [rcx+1Ch], ebp
0x18004778a  jz      short loc_1800477A6
0x18004778c  cmp     byte ptr [rcx+19h], 6
0x180047790  jb      short loc_1800477A6
0x180047792  mov     rcx, [rcx+10h]
0x180047796  mov     edx, 2B6h
0x18004779b  mov     r9d, ebx
0x18004779e  mov     r8, r15
0x1800477a1  call    WPP_SF_d
0x1800477a6  mov     eax, ebx
0x1800477a8  add     rsp, 38h
0x1800477ac  pop     r15
0x1800477ae  pop     r14
0x1800477b0  pop     rdi
0x1800477b1  pop     rsi
0x1800477b2  pop     rbp
0x1800477b3  pop     rbx
0x1800477b4  retn
```
