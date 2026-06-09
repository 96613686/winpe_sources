# ReadMiniRdrParameters

- ea: `0x140020540`
- end: `0x1400207e7`
- name: `ReadMiniRdrParameters`
- size: `679`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14008fbc0`
- `0x1400926fc`

## callees

- `0x140020540`
- `0x14003838c`
- `0x140059dc0`
- `0x1400904c0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140020680`
- `ntoskrnl!ZwOpenKey` at `0x140020680`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14005e5e2`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14005e5e2`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14002059f`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14002059f`
- `ntoskrnl!ZwClose` at `0x14005e6a3`
- `ntoskrnl!ZwClose` at `0x14005e6a3`

## string_xrefs

- `0x1400205f6`: `\Registry\Machine\System\CurrentControlSet\Services\MRxSmb\Parameters`
- `0x14005e5c1`: `\Registry\Machine\System\CurrentControlSet\Services\MRxSmb\Parameters`

## pseudocode

```c
int ReadMiniRdrParameters()
{
  __int64 v0; // rax
  const wchar_t *v1; // rdx
  unsigned __int64 v2; // r8
  char *v3; // r9
  unsigned int v4; // edi
  __int16 v5; // r10
  unsigned __int16 v6; // r10
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // r9
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v14; // [rsp+48h] [rbp-B8h] BYREF
  char *v15; // [rsp+50h] [rbp-B0h]
  int v16; // [rsp+58h] [rbp-A8h] BYREF
  void *KeyHandle; // [rsp+60h] [rbp-A0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  char v19; // [rsp+A0h] [rbp-60h] BYREF

  v14 = 34078720;
  KeyHandle = 0;
  v15 = &v19;
  memset(&ObjectAttributes, 0, 44);
  v16 = 0;
  if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
  {
    LODWORD(v0) = WORD1(v14);
    if ( v15 )
    {
      v1 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\MRxSmb\\Parameters";
      v2 = (unsigned __int64)WORD1(v14) >> 1;
      v0 = 0x7FFF;
      v3 = v15;
      v4 = 0;
      v5 = 0;
      if ( v2 )
      {
        while ( v0 && *v1 )
        {
          *(_WORD *)v3 = *v1++;
          v3 += 2;
          --v0;
          ++v5;
          if ( !--v2 )
          {
            if ( !v0 || !*v1 )
              break;
            goto LABEL_4;
          }
        }
      }
      else
      {
LABEL_4:
        v4 = -2147483643;
      }
      v6 = 2 * v5;
      LOWORD(v14) = v6;
      if ( (v4 & 0x80000000) == 0 )
        goto LABEL_6;
    }
    else
    {
      v4 = -1073741811;
    }
    v8 = v4;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_16;
    LODWORD(v0) = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (v0 & 1) == 0 || !BYTE1(WPP_GLOBAL_Control->Timer) )
      goto LABEL_16;
    v10 = 35;
LABEL_38:
    LODWORD(v0) = WPP_SF_d(v9->AttachedDevice, v10, &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids, v8);
    goto LABEL_16;
  }
  LODWORD(v0) = RtlGetPersistedStateLocation(
                  L"MRxSmbParameters",
                  0,
                  L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\MRxSmb\\Parameters",
                  0,
                  v15,
                  WORD1(v14),
                  &v16);
  v4 = v0;
  if ( (int)v0 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_16;
    LODWORD(v0) = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (v0 & 1) == 0 || !BYTE1(WPP_GLOBAL_Control->Timer) )
      goto LABEL_16;
    v10 = 34;
    v8 = v4;
    goto LABEL_38;
  }
  v6 = v16 - 2;
  LOWORD(v14) = v16 - 2;
LABEL_6:
  LODWORD(v0) = WORD1(v14);
  if ( (unsigned __int64)v6 + 2 <= WORD1(v14) )
  {
    *(_WORD *)&v15[v6] = 0;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v14;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    LODWORD(v0) = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( (int)v0 >= 0 )
    {
      if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
        byte_14007D166 = 0;
      if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
        MRxSmbObeyBindingOrder = 1;
      if ( (int)MRxSmbGetUlongRegistryParameter(KeyHandle) >= 0 )
        MRxSmbEnforceTransportBindings = 0;
      LODWORD(v0) = ZwClose(KeyHandle);
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v11 = 41;
        v12 = (unsigned int)v0;
        goto LABEL_44;
      }
    }
    return v0;
  }
  v4 = -1073741789;
LABEL_16:
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    LODWORD(v0) = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (v0 & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v11 = 40;
        v12 = v4;
LABEL_44:
        LODWORD(v0) = WPP_SF_d(v7->AttachedDevice, v11, &WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids, v12);
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x140020540  mov     [rsp-8+arg_0], rbx
0x140020545  mov     [rsp-8+arg_8], rdi
0x14002054a  push    rbp
0x14002054b  lea     rbp, [rsp-1C0h]
0x140020553  sub     rsp, 2C0h
0x14002055a  mov     rax, cs:__security_cookie
0x140020561  xor     rax, rsp
0x140020564  mov     [rbp+1C0h+var_10], rax
0x14002056b  xorps   xmm0, xmm0
0x14002056e  mov     [rsp+2C0h+var_278], 2080000h
0x140020577  xor     ebx, ebx
0x140020579  xor     eax, eax
0x14002057b  lea     rax, [rbp+1C0h+var_220]
0x14002057f  mov     [rsp+2C0h+KeyHandle], rbx
0x140020584  movups  xmmword ptr [rsp+2C0h+ObjectAttributes.ObjectName], xmm0
0x140020589  mov     [rsp+2C0h+var_270], rax
0x14002058e  movups  xmmword ptr [rsp+2C0h+ObjectAttributes.Length], xmm0
0x140020593  mov     [rsp+2C0h+var_280], ebx
0x140020597  movups  xmmword ptr [rbp+1C0h+ObjectAttributes+1Ch], xmm0
0x14002059b  mov     [rsp+2C0h+var_268], ebx
0x14002059f  call    cs:__imp_RtlIsStateSeparationEnabled
0x1400205a6  nop     dword ptr [rax+rax+00h]
0x1400205ab  test    al, al
0x1400205ad  jnz     loc_14005E5B2
0x1400205b3  movzx   ecx, word ptr [rsp+2C0h+var_278]
0x1400205b8  test    cl, 1
0x1400205bb  jnz     loc_1400206D8
0x1400205c1  movzx   eax, word ptr [rsp+2C0h+var_278+2]
0x1400205c6  test    al, 1
0x1400205c8  jnz     loc_1400206D8
0x1400205ce  cmp     cx, ax
0x1400205d1  ja      loc_1400206D8
0x1400205d7  mov     edx, 0FFFEh
0x1400205dc  cmp     ax, dx
0x1400205df  ja      loc_1400206D8
0x1400205e5  cmp     [rsp+2C0h+var_270], rbx
0x1400205ea  jz      loc_14002078B
0x1400205f0  movzx   r8d, word ptr [rsp+2C0h+var_278+2]
0x1400205f6  lea     rdx, aRegistryMachin_15; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400205fd  shr     r8, 1
0x140020600  mov     eax, 7FFFh
0x140020605  mov     r9, [rsp+2C0h+var_270]
0x14002060a  mov     edi, ebx
0x14002060c  mov     r10, rbx
0x14002060f  jnz     loc_140020740
0x140020615  mov     edi, 80000005h
0x14002061a  add     r10w, r10w
0x14002061e  mov     word ptr [rsp+2C0h+var_278], r10w
0x140020624  test    edi, edi
0x140020626  js      loc_1400206DD
0x14002062c  movzx   eax, word ptr [rsp+2C0h+var_278+2]
0x140020631  movzx   edx, r10w
0x140020635  lea     rcx, [rdx+2]
0x140020639  cmp     rcx, rax
0x14002063c  ja      loc_14002070A
0x140020642  mov     rax, [rsp+2C0h+var_270]
0x140020647  lea     r8, [rsp+2C0h+ObjectAttributes]; ObjectAttributes
0x14002064c  xorps   xmm0, xmm0
0x14002064f  lea     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x140020654  mov     [rdx+rax], bx
0x140020658  lea     rax, [rsp+2C0h+var_278]
0x14002065d  mov     edx, 20019h; DesiredAccess
0x140020662  mov     [rsp+2C0h+ObjectAttributes.ObjectName], rax
0x140020667  mov     [rsp+2C0h+ObjectAttributes.Length], 30h ; '0'
0x14002066f  mov     [rsp+2C0h+ObjectAttributes.RootDirectory], rbx
0x140020674  mov     [rbp+1C0h+ObjectAttributes.Attributes], 240h
0x14002067b  movdqu  xmmword ptr [rbp+1C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x140020680  call    cs:__imp_ZwOpenKey
0x140020687  nop     dword ptr [rax+rax+00h]
0x14002068c  test    eax, eax
0x14002068e  jns     loc_1400207B9
0x140020694  mov     rcx, cs:WPP_GLOBAL_Control
0x14002069b  lea     rbx, WPP_GLOBAL_Control
0x1400206a2  cmp     rcx, rbx
0x1400206a5  jz      short loc_1400206B3
0x1400206a7  mov     edx, [rcx+2Ch]
0x1400206aa  test    dl, 1
0x1400206ad  jnz     loc_1400207A2
0x1400206b3  mov     rcx, [rbp+1C0h+var_10]
0x1400206ba  xor     rcx, rsp; StackCookie
0x1400206bd  call    __security_check_cookie
0x1400206c2  lea     r11, [rsp+2C0h+var_s0]
0x1400206ca  mov     rbx, [r11+10h]
0x1400206ce  mov     rdi, [r11+18h]
0x1400206d2  mov     rsp, r11
0x1400206d5  pop     rbp
0x1400206d6  retn
0x1400206d8  mov     edi, 0C000000Dh
0x1400206dd  mov     r9d, edi
0x1400206e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400206e7  lea     rbx, WPP_GLOBAL_Control
0x1400206ee  cmp     rcx, rbx
0x1400206f1  jz      short loc_140020716
0x1400206f3  mov     eax, [rcx+2Ch]
0x1400206f6  test    al, 1
0x1400206f8  jz      short loc_140020716
0x1400206fa  cmp     byte ptr [rcx+29h], 1
0x1400206fe  jb      short loc_140020716
0x140020700  mov     edx, 23h ; '#'
0x140020705  jmp     loc_14005E63E
0x14002070a  mov     edi, 0C0000023h
0x14002070f  lea     rbx, WPP_GLOBAL_Control
0x140020716  mov     rcx, cs:WPP_GLOBAL_Control
0x14002071d  cmp     rcx, rbx
0x140020720  jz      short loc_1400206B3
0x140020722  mov     eax, [rcx+2Ch]
0x140020725  test    al, 1
0x140020727  jz      short loc_1400206B3
0x140020729  cmp     byte ptr [rcx+29h], 1
0x14002072d  jb      short loc_1400206B3
0x14002072f  mov     edx, 28h ; '('
0x140020734  mov     r9d, edi
0x140020737  jmp     loc_14005E6B5
0x140020740  test    rax, rax
0x140020743  jz      loc_14002061A
0x140020749  movzx   ecx, word ptr [rdx]
0x14002074c  test    cx, cx
0x14002074f  jz      short loc_140020780
0x140020751  mov     [r9], cx
0x140020755  add     rdx, 2
0x140020759  add     r9, 2
0x14002075d  dec     rax
0x140020760  inc     r10
0x140020763  sub     r8, 1
0x140020767  jnz     short loc_140020740
0x140020769  test    rax, rax
0x14002076c  jz      loc_14002061A
0x140020772  cmp     [rdx], bx
0x140020775  jz      loc_14002061A
0x14002077b  jmp     loc_140020615
0x140020780  test    r8, r8
0x140020783  jnz     loc_14002061A
0x140020789  jmp     short loc_140020769
0x14002078b  test    cx, cx
0x14002078e  jnz     loc_1400206D8
0x140020794  test    ax, ax
0x140020797  jnz     loc_1400206D8
0x14002079d  jmp     loc_1400205F0
0x1400207a2  cmp     byte ptr [rcx+29h], 1
0x1400207a6  jb      loc_1400206B3
0x1400207ac  mov     edx, 29h ; ')'
0x1400207b1  mov     r9d, eax
0x1400207b4  jmp     loc_14005E6B5
0x1400207b9  mov     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x1400207be  lea     r8, [rsp+2C0h+var_280]
0x1400207c3  lea     rdx, aDisableshadowl; "DisableShadowLoopback"
0x1400207ca  call    MRxSmbGetUlongRegistryParameter
0x1400207cf  test    eax, eax
0x1400207d1  js      loc_14005E654
0x1400207d7  cmp     [rsp+2C0h+var_280], ebx
0x1400207db  setnz   cs:byte_14007D166
0x1400207e2  jmp     loc_14005E654
0x14005e5b2  movzx   eax, word ptr [rsp+2C0h+var_278+2]
0x14005e5b7  lea     rcx, [rsp+2C0h+var_268]
0x14005e5bc  mov     [rsp+2C0h+var_290], rcx
0x14005e5c1  lea     r8, aRegistryMachin_15; "\\Registry\\Machine\\System\\CurrentCon"...
0x14005e5c8  mov     [rsp+2C0h+var_298], eax
0x14005e5cc  lea     rcx, aMrxsmbparamete; "MRxSmbParameters"
0x14005e5d3  mov     rax, [rsp+2C0h+var_270]
0x14005e5d8  xor     r9d, r9d
0x14005e5db  xor     edx, edx
0x14005e5dd  mov     [rsp+2C0h+var_2A0], rax
0x14005e5e2  call    cs:__imp_RtlGetPersistedStateLocation
0x14005e5e9  nop     dword ptr [rax+rax+00h]
0x14005e5ee  mov     edi, eax
0x14005e5f0  test    eax, eax
0x14005e5f2  js      short loc_14005E60A
0x14005e5f4  movzx   r10d, word ptr [rsp+2C0h+var_268]
0x14005e5fa  sub     r10w, 2
0x14005e5ff  mov     word ptr [rsp+2C0h+var_278], r10w
0x14005e605  jmp     loc_14002062C
0x14005e60a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e611  lea     rbx, WPP_GLOBAL_Control
0x14005e618  cmp     rcx, rbx
0x14005e61b  jz      loc_140020716
0x14005e621  mov     eax, [rcx+2Ch]
0x14005e624  test    al, 1
0x14005e626  jz      loc_140020716
0x14005e62c  cmp     byte ptr [rcx+29h], 1
0x14005e630  jb      loc_140020716
0x14005e636  mov     edx, 22h ; '"'
0x14005e63b  mov     r9d, edi
0x14005e63e  mov     rcx, [rcx+18h]
0x14005e642  lea     r8, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids
0x14005e649  call    WPP_SF_d
0x14005e64e  nop
0x14005e64f  jmp     loc_140020716
0x14005e654  mov     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x14005e659  lea     r8, [rsp+2C0h+var_280]
0x14005e65e  lea     rdx, aIgnorebindingo; "IgnoreBindingOrder"
0x14005e665  call    MRxSmbGetUlongRegistryParameter
0x14005e66a  test    eax, eax
0x14005e66c  js      short loc_14005E679
0x14005e66e  cmp     byte ptr [rsp+2C0h+var_280], bl
0x14005e672  setz    cs:MRxSmbObeyBindingOrder
0x14005e679  mov     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x14005e67e  lea     r8, [rsp+2C0h+var_280]
0x14005e683  lea     rdx, aEnforcetranspo; "EnforceTransportBindings"
0x14005e68a  call    MRxSmbGetUlongRegistryParameter
0x14005e68f  test    eax, eax
0x14005e691  js      short loc_14005E69E
0x14005e693  cmp     [rsp+2C0h+var_280], ebx
0x14005e697  setnz   cs:MRxSmbEnforceTransportBindings
0x14005e69e  mov     rcx, [rsp+2C0h+KeyHandle]; Handle
0x14005e6a3  call    cs:__imp_ZwClose
0x14005e6aa  nop     dword ptr [rax+rax+00h]
0x14005e6af  nop
0x14005e6b0  jmp     loc_1400206B3
0x14005e6b5  mov     rcx, [rcx+18h]
0x14005e6b9  lea     r8, WPP_4ff68d8e9b0a3e70c0197c268f5ae5e8_Traceguids
0x14005e6c0  call    WPP_SF_d
0x14005e6c5  nop
0x14005e6c6  jmp     loc_1400206B3
```
