# BthServPushPolicyValue(HKEY__ *,BthPolicy)

- ea: `0x18001e028`
- end: `0x18001e1d6`
- name: `?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001e1dc`

## callees

- `0x18001e028`
- `0x18001e8b4`
- `0x180031f04`
- `0x180031fd8`
- `0x180032190`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e149`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e149`

## pseudocode

```c
LSTATUS __fastcall BthServPushPolicyValue(HKEY a1, unsigned int a2)
{
  int PolicyValue; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  char v8; // bl
  bool v9; // r11
  __int64 v10; // r10
  char v11; // r11
  int v12; // edx
  int v13; // r8d
  const WCHAR *PolicyKeyValueName; // rax
  LSTATUS result; // eax
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // r10
  int v20; // edx
  char v21; // r11
  int v22; // r8d
  int Data; // [rsp+90h] [rbp+18h] BYREF

  Data = 0;
  PolicyValue = BthGetPolicyValue(a2, &Data);
  v7 = (unsigned int)PolicyValue;
  v8 = 1;
  if ( PolicyValue >= 0 )
    goto LABEL_22;
  v5 = a2 - 1;
  if ( a2 == 1 )
  {
    Data = 2;
    goto LABEL_15;
  }
  v5 = a2 - 2;
  if ( a2 == 2 )
    goto LABEL_13;
  v5 = a2 - 4;
  if ( a2 == 4 )
    goto LABEL_13;
  v5 = a2 - 8;
  if ( a2 == 8 )
    goto LABEL_13;
  v5 = a2 - 16;
  if ( a2 == 16 )
    goto LABEL_13;
  v5 = a2 - 32;
  if ( a2 == 32 )
    goto LABEL_12;
  v5 = a2 - 64;
  if ( a2 == 64 )
    goto LABEL_12;
  v5 = a2 - 1024;
  if ( a2 == 1024 )
  {
LABEL_13:
    Data = 1;
    goto LABEL_15;
  }
  if ( a2 == 2048 )
  {
LABEL_12:
    Data = 0;
    goto LABEL_15;
  }
  Data = -1;
LABEL_15:
  v9 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
  LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    BthGetPolicyName(a2, v5, v6, (unsigned int)PolicyValue);
    LOBYTE(v12) = v11;
    WPP_RECORDER_AND_TRACE_SF_sSD(*(_QWORD *)(v10 + 16), v12, v13, *(_QWORD *)(v10 + 40));
  }
LABEL_22:
  PolicyKeyValueName = (const WCHAR *)BthGetPolicyKeyValueName(a2, v5, v6, v7);
  result = RegSetKeyValueW(a1, 0, PolicyKeyValueName, 4u, &Data, 4u);
  v18 = (unsigned int)result;
  if ( result > 0 )
    v18 = (unsigned __int16)result | 0x80070000;
  if ( (int)v18 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v8 = 0;
    if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      BthGetPolicyName(a2, v16, v18, v17);
      LOBYTE(v20) = v8;
      LOBYTE(v22) = v21;
      return WPP_RECORDER_AND_TRACE_SF_sSD(*(_QWORD *)(v19 + 16), v20, v22, *(_QWORD *)(v19 + 40));
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001e028  mov     rax, rsp
0x18001e02b  mov     [rax+8], rbx
0x18001e02f  mov     [rax+10h], rsi
0x18001e033  push    rdi
0x18001e034  push    r14
0x18001e036  push    r15
0x18001e038  sub     rsp, 60h
0x18001e03c  and     dword ptr [rax+18h], 0
0x18001e040  mov     edi, edx
0x18001e042  mov     rsi, rcx
0x18001e045  lea     rdx, [rax+18h]
0x18001e049  mov     ecx, edi
0x18001e04b  call    BthGetPolicyValue
0x18001e050  lea     r14, WPP_GLOBAL_Control
0x18001e057  mov     r9d, eax
0x18001e05a  lea     r15, WPP_RECORDER_INITIALIZED
0x18001e061  mov     ebx, 1
0x18001e066  test    eax, eax
0x18001e068  jns     loc_18001E121
0x18001e06e  mov     edx, edi
0x18001e070  sub     edx, ebx
0x18001e072  jz      short loc_18001E0BE
0x18001e074  sub     edx, ebx
0x18001e076  jz      short loc_18001E0B5
0x18001e078  sub     edx, 2
0x18001e07b  jz      short loc_18001E0B5
0x18001e07d  sub     edx, 4
0x18001e080  jz      short loc_18001E0B5
0x18001e082  sub     edx, 8
0x18001e085  jz      short loc_18001E0B5
0x18001e087  sub     edx, 10h
0x18001e08a  jz      short loc_18001E0AB
0x18001e08c  sub     edx, 20h ; ' '
0x18001e08f  jz      short loc_18001E0AB
0x18001e091  sub     edx, 3C0h
0x18001e097  jz      short loc_18001E0B5
0x18001e099  cmp     edx, 400h
0x18001e09f  jz      short loc_18001E0AB
0x18001e0a1  or      [rsp+78h+Data], 0FFFFFFFFh
0x18001e0a9  jmp     short loc_18001E0C9
0x18001e0ab  and     [rsp+78h+Data], 0
0x18001e0b3  jmp     short loc_18001E0C9
0x18001e0b5  mov     [rsp+78h+Data], ebx
0x18001e0bc  jmp     short loc_18001E0C9
0x18001e0be  mov     [rsp+78h+Data], 2
0x18001e0c9  mov     r10, cs:WPP_GLOBAL_Control
0x18001e0d0  cmp     r10, r14
0x18001e0d3  jz      short loc_18001E0E1
0x18001e0d5  cmp     byte ptr [r10+19h], 3
0x18001e0da  jb      short loc_18001E0E1
0x18001e0dc  mov     r11b, bl
0x18001e0df  jmp     short loc_18001E0E4
0x18001e0e1  xor     r11b, r11b
0x18001e0e4  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001e0eb  setnz   r8b
0x18001e0ef  test    r11b, r11b
0x18001e0f2  jnz     short loc_18001E0F9
0x18001e0f4  test    r8b, r8b
0x18001e0f7  jz      short loc_18001E121
0x18001e0f9  mov     ecx, edi
0x18001e0fb  call    BthGetPolicyName
0x18001e100  mov     rcx, [r10+10h]
0x18001e104  mov     dl, r11b
0x18001e107  mov     [rsp+78h+var_28], r9d
0x18001e10c  mov     r9, [r10+28h]
0x18001e110  mov     [rsp+78h+var_30], rax
0x18001e115  mov     [rsp+78h+var_48], 0Ah
0x18001e11c  call    WPP_RECORDER_AND_TRACE_SF_sSD
0x18001e121  mov     ecx, edi
0x18001e123  call    BthGetPolicyKeyValueName
0x18001e128  xor     edx, edx; lpSubKey
0x18001e12a  mov     [rsp+78h+cbData], 4; cbData
0x18001e132  mov     r8, rax; lpValueName
0x18001e135  mov     rcx, rsi; hKey
0x18001e138  lea     rax, [rsp+78h+Data]
0x18001e140  mov     [rsp+78h+lpData], rax; lpData
0x18001e145  lea     r9d, [rdx+4]; dwType
0x18001e149  call    cs:__imp_RegSetKeyValueW
0x18001e150  nop     dword ptr [rax+rax+00h]
0x18001e155  mov     r8d, eax
0x18001e158  test    eax, eax
0x18001e15a  jle     short loc_18001E167
0x18001e15c  movzx   r8d, ax
0x18001e160  or      r8d, 80070000h
0x18001e167  test    r8d, r8d
0x18001e16a  jns     short loc_18001E1BF
0x18001e16c  mov     r10, cs:WPP_GLOBAL_Control
0x18001e173  cmp     r10, r14
0x18001e176  jz      short loc_18001E17F
0x18001e178  cmp     byte ptr [r10+19h], 2
0x18001e17d  jnb     short loc_18001E181
0x18001e17f  xor     bl, bl
0x18001e181  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001e188  setnz   r11b
0x18001e18c  test    bl, bl
0x18001e18e  jnz     short loc_18001E195
0x18001e190  test    r11b, r11b
0x18001e193  jz      short loc_18001E1BF
0x18001e195  mov     ecx, edi
0x18001e197  call    BthGetPolicyName
0x18001e19c  mov     rcx, [r10+10h]
0x18001e1a0  mov     dl, bl
0x18001e1a2  mov     r9, [r10+28h]
0x18001e1a6  mov     [rsp+78h+var_28], r8d
0x18001e1ab  mov     r8b, r11b
0x18001e1ae  mov     [rsp+78h+var_30], rax
0x18001e1b3  mov     [rsp+78h+var_48], 0Bh
0x18001e1ba  call    WPP_RECORDER_AND_TRACE_SF_sSD
0x18001e1bf  lea     r11, [rsp+78h+var_18]
0x18001e1c4  mov     rbx, [r11+20h]
0x18001e1c8  mov     rsi, [r11+28h]
0x18001e1cc  mov     rsp, r11
0x18001e1cf  pop     r15
0x18001e1d1  pop     r14
0x18001e1d3  pop     rdi
0x18001e1d4  retn
```
