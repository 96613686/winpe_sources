# BthServBluetoothControlPanelTasksSetState(int)

- ea: `0x18000ba9c`
- end: `0x18000bcdf`
- name: `?BthServBluetoothControlPanelTasksSetState@@YAXH@Z`
- size: `579`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18000bce8`
- `0x18000db08`

## callees

- `0x18000ba9c`
- `0x180012004`
- `0x1800120b8`
- `0x180012384`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bb3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bb3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bc6c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bbbb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bbbb`

## string_xrefs

- `0x18000bb2f`: `SYSTEM\CurrentControlSet\Services\BthServ\Parameters\BluetoothControlPanelTasks`

## pseudocode

```c
void __fastcall BthServBluetoothControlPanelTasksSetState(int a1)
{
  char v1; // bl
  bool v2; // dl
  int v3; // edx
  int v4; // r8d
  _QWORD *v5; // rcx
  BOOL Data; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  hKey = 0;
  Data = a1 != 0;
  v1 = 1;
  v2 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\BthServ\\Parameters\\BluetoothControlPanelTasks",
         0,
         0x20006u,
         &hKey) )
  {
    v5 = WPP_GLOBAL_Control;
    LOBYTE(v3) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_30:
      WPP_RECORDER_AND_TRACE_SF_sD(v5[2], v3, v4, v5[5]);
      v5 = WPP_GLOBAL_Control;
    }
  }
  else if ( RegSetValueExW(hKey, L"State", 0, 4u, (const BYTE *)&Data, 4u) )
  {
    v5 = WPP_GLOBAL_Control;
    LOBYTE(v3) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_30;
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    LOBYTE(v3) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
    LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_30;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 == &WPP_GLOBAL_Control || *((_BYTE *)v5 + 25) < 5u )
    v1 = 0;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v3) = v1;
    LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_si(v5[2], v3, v4, v5[5]);
  }
}

```

## disassembly

```asm
0x18000ba9c  mov     [rsp+arg_10], rbx
0x18000baa1  mov     [rsp+arg_18], rsi
0x18000baa6  push    rdi
0x18000baa7  push    r14
0x18000baa9  push    r15
0x18000baab  sub     rsp, 50h
0x18000baaf  and     [rsp+68h+hKey], 0
0x18000bab5  xor     eax, eax
0x18000bab7  test    ecx, ecx
0x18000bab9  setnz   al
0x18000babc  mov     [rsp+68h+Data], eax
0x18000bac0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bac7  lea     rsi, WPP_GLOBAL_Control
0x18000bace  mov     bl, 1
0x18000bad0  cmp     rcx, rsi
0x18000bad3  jz      short loc_18000BADF
0x18000bad5  cmp     byte ptr [rcx+19h], 5
0x18000bad9  jb      short loc_18000BADF
0x18000badb  mov     dl, bl
0x18000badd  jmp     short loc_18000BAE1
0x18000badf  xor     dl, dl
0x18000bae1  lea     r14, WPP_RECORDER_INITIALIZED
0x18000bae8  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000baef  lea     r15, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000baf6  setnz   r8b
0x18000bafa  test    dl, dl
0x18000bafc  jnz     short loc_18000BB03
0x18000bafe  test    r8b, r8b
0x18000bb01  jz      short loc_18000BB1C
0x18000bb03  mov     r9, [rcx+28h]
0x18000bb07  mov     rcx, [rcx+10h]
0x18000bb0b  mov     [rsp+68h+var_30], r15
0x18000bb10  mov     [rsp+68h+var_38], 4Ch ; 'L'
0x18000bb17  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000bb1c  lea     rax, [rsp+68h+hKey]
0x18000bb21  mov     r9d, 20006h; samDesired
0x18000bb27  xor     r8d, r8d; ulOptions
0x18000bb2a  mov     [rsp+68h+phkResult], rax; phkResult
0x18000bb2f  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Bt"...
0x18000bb36  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bb3d  call    cs:__imp_RegOpenKeyExW
0x18000bb44  nop     dword ptr [rax+rax+00h]
0x18000bb49  mov     edi, eax
0x18000bb4b  test    eax, eax
0x18000bb4d  jz      short loc_18000BB94
0x18000bb4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb56  cmp     rcx, rsi
0x18000bb59  jz      short loc_18000BB65
0x18000bb5b  cmp     byte ptr [rcx+19h], 2
0x18000bb5f  jb      short loc_18000BB65
0x18000bb61  mov     dl, bl
0x18000bb63  jmp     short loc_18000BB67
0x18000bb65  xor     dl, dl
0x18000bb67  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000bb6e  setnz   r8b
0x18000bb72  test    dl, dl
0x18000bb74  jnz     short loc_18000BB7F
0x18000bb76  test    r8b, r8b
0x18000bb79  jz      loc_18000BC5F
0x18000bb7f  mov     dword ptr [rsp+68h+var_20], eax
0x18000bb83  mov     [rsp+68h+var_30], r15
0x18000bb88  mov     [rsp+68h+var_38], 4Dh ; 'M'
0x18000bb8f  jmp     loc_18000BC4B
0x18000bb94  mov     rcx, [rsp+68h+hKey]; hKey
0x18000bb99  lea     rax, [rsp+68h+Data]
0x18000bb9e  mov     [rsp+68h+cbData], 4; cbData
0x18000bba6  lea     rdx, ValueName; "State"
0x18000bbad  mov     r9d, 4; dwType
0x18000bbb3  mov     [rsp+68h+phkResult], rax; lpData
0x18000bbb8  xor     r8d, r8d; Reserved
0x18000bbbb  call    cs:__imp_RegSetValueExW
0x18000bbc2  nop     dword ptr [rax+rax+00h]
0x18000bbc7  mov     edi, eax
0x18000bbc9  test    eax, eax
0x18000bbcb  jz      short loc_18000BC0B
0x18000bbcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbd4  cmp     rcx, rsi
0x18000bbd7  jz      short loc_18000BBE3
0x18000bbd9  cmp     byte ptr [rcx+19h], 2
0x18000bbdd  jb      short loc_18000BBE3
0x18000bbdf  mov     dl, bl
0x18000bbe1  jmp     short loc_18000BBE5
0x18000bbe3  xor     dl, dl
0x18000bbe5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000bbec  setnz   r8b
0x18000bbf0  test    dl, dl
0x18000bbf2  jnz     short loc_18000BBF9
0x18000bbf4  test    r8b, r8b
0x18000bbf7  jz      short loc_18000BC5F
0x18000bbf9  mov     dword ptr [rsp+68h+var_20], eax
0x18000bbfd  mov     [rsp+68h+var_30], r15
0x18000bc02  mov     [rsp+68h+var_38], 4Eh ; 'N'
0x18000bc09  jmp     short loc_18000BC4B
0x18000bc0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc12  cmp     rcx, rsi
0x18000bc15  jz      short loc_18000BC21
0x18000bc17  cmp     byte ptr [rcx+19h], 4
0x18000bc1b  jb      short loc_18000BC21
0x18000bc1d  mov     dl, bl
0x18000bc1f  jmp     short loc_18000BC23
0x18000bc21  xor     dl, dl
0x18000bc23  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000bc2a  setnz   r8b
0x18000bc2e  test    dl, dl
0x18000bc30  jnz     short loc_18000BC37
0x18000bc32  test    r8b, r8b
0x18000bc35  jz      short loc_18000BC5F
0x18000bc37  mov     eax, [rsp+68h+Data]
0x18000bc3b  mov     dword ptr [rsp+68h+var_20], eax
0x18000bc3f  mov     [rsp+68h+var_30], r15
0x18000bc44  mov     [rsp+68h+var_38], 4Fh ; 'O'
0x18000bc4b  mov     r9, [rcx+28h]
0x18000bc4f  mov     rcx, [rcx+10h]
0x18000bc53  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18000bc58  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc5f  mov     rax, [rsp+68h+hKey]
0x18000bc64  test    rax, rax
0x18000bc67  jz      short loc_18000BC85
0x18000bc69  mov     rcx, rax; hKey
0x18000bc6c  call    cs:__imp_RegCloseKey
0x18000bc73  nop     dword ptr [rax+rax+00h]
0x18000bc78  and     [rsp+68h+hKey], 0
0x18000bc7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc85  cmp     rcx, rsi
0x18000bc88  jz      short loc_18000BC90
0x18000bc8a  cmp     byte ptr [rcx+19h], 5
0x18000bc8e  jnb     short loc_18000BC92
0x18000bc90  xor     bl, bl
0x18000bc92  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000bc99  setnz   r8b
0x18000bc9d  test    bl, bl
0x18000bc9f  jnz     short loc_18000BCA6
0x18000bca1  test    r8b, r8b
0x18000bca4  jz      short loc_18000BCC8
0x18000bca6  mov     r9, [rcx+28h]
0x18000bcaa  mov     dl, bl
0x18000bcac  mov     rcx, [rcx+10h]
0x18000bcb0  mov     eax, edi
0x18000bcb2  mov     [rsp+68h+var_20], rax
0x18000bcb7  mov     [rsp+68h+var_30], r15
0x18000bcbc  mov     [rsp+68h+var_38], 50h ; 'P'
0x18000bcc3  call    WPP_RECORDER_AND_TRACE_SF_si
0x18000bcc8  lea     r11, [rsp+68h+var_18]
0x18000bccd  mov     rbx, [r11+30h]
0x18000bcd1  mov     rsi, [r11+38h]
0x18000bcd5  mov     rsp, r11
0x18000bcd8  pop     r15
0x18000bcda  pop     r14
0x18000bcdc  pop     rdi
0x18000bcdd  retn
```
