# EVENT_LOG::ReportIncorrectHTTPReply(GenericStringHandle<ushort>,SidHandle,_GUID const &,ushort const *,_GUID const &,ushort const *,long,unsigned __int64,ushort const *,ushort const *)

- ea: `0x1800b5b34`
- end: `0x1800b5d50`
- name: `?ReportIncorrectHTTPReply@EVENT_LOG@@QEAAJV?$GenericStringHandle@G@@VSidHandle@@AEBU_GUID@@PEBG23J_K33@Z`
- size: `540`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800724d0`
- `0x1800bfbf0`

## callees

- `0x180016d60`
- `0x18001d7f0`
- `0x180066e20`
- `0x1800717e0`
- `0x180085abc`
- `0x18009d024`
- `0x1800a3420`
- `0x1800ab7b0`
- `0x1800b5b34`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x1800b5bde`
- `ntdll!EtwEventEnabled` at `0x1800b5bde`
- `ntdll!EtwEventActivityIdControl` at `0x1800b5cfc`
- `ntdll!EtwEventActivityIdControl` at `0x1800b5d0e`
- `ntdll!EtwEventActivityIdControl` at `0x1800b5cfc`
- `ntdll!EtwEventActivityIdControl` at `0x1800b5d0e`
- `ntdll!EtwEventWrite` at `0x1800b5ca2`
- `ntdll!EtwEventWrite` at `0x1800b5ca2`

## pseudocode

```c
__int64 __fastcall EVENT_LOG::ReportIncorrectHTTPReply(
        __int64 a1,
        __int64 a2,
        PSID *a3,
        __int64 a4,
        unsigned __int16 *a5,
        struct _GUID *a6,
        unsigned __int16 *a7,
        char a8,
        char a9,
        unsigned __int16 *a10,
        unsigned __int16 *a11)
{
  EVENT_LOG *v12; // rbx
  EVENT_LOG *v15; // rcx
  signed int v16; // ebx
  EVENT_LOG *v17; // rcx
  EVENT_LOG *v18; // rcx
  EVENT_LOG *v19; // rcx
  EVENT_LOG *v20; // rcx
  unsigned __int16 *v22; // [rsp+30h] [rbp-C9h]
  unsigned __int16 *v23; // [rsp+38h] [rbp-C1h]
  _BYTE v24[16]; // [rsp+40h] [rbp-B9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v25; // [rsp+50h] [rbp-A9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+60h] [rbp-99h] BYREF
  __int64 v27; // [rsp+70h] [rbp-89h]
  __int64 v28; // [rsp+78h] [rbp-81h]
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+80h] [rbp-79h] BYREF
  struct _GUID *v30; // [rsp+90h] [rbp-69h]
  __int64 v31; // [rsp+98h] [rbp-61h]
  struct _EVENT_DATA_DESCRIPTOR v32; // [rsp+A0h] [rbp-59h] BYREF
  char *v33; // [rsp+B0h] [rbp-49h]
  __int64 v34; // [rsp+B8h] [rbp-41h]
  char *v35; // [rsp+C0h] [rbp-39h]
  __int64 v36; // [rsp+C8h] [rbp-31h]
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+D0h] [rbp-29h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v38; // [rsp+E0h] [rbp-19h] BYREF

  v12 = g_EventLogger;
  v22 = a10;
  v23 = a11;
  if ( !*(_QWORD *)g_EventLogger )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids);
    goto LABEL_6;
  }
  EVENT_LOG::SidToUser(*a3, *((LPWSTR *)g_EventLogger + 1), (__int64)a3);
  if ( !(unsigned __int8)EtwEventEnabled(*(_QWORD *)v12, &EVT_INCORRECT_HTTP_REPLY) )
  {
LABEL_6:
    v16 = 0;
    goto LABEL_15;
  }
  EVENT_LOG::EventDataDescCreate_UnicodeString(v15, &v25, (const unsigned __int16 *)(*(_QWORD *)a2 + 12LL));
  EVENT_LOG::EventDataDescCreate_UnicodeString(v17, &v26, *((const unsigned __int16 **)v12 + 1));
  v27 = a4;
  v28 = 16;
  EVENT_LOG::EventDataDescCreate_UnicodeString(v18, &v29, a5);
  v30 = a6;
  v31 = 16;
  EVENT_LOG::EventDataDescCreate_UnicodeString(v19, &v32, a7);
  v35 = &a9;
  v33 = &a8;
  v34 = 4;
  v36 = 8;
  EVENT_LOG::EventDataDescCreate_UnicodeString((EVENT_LOG *)&a8, &v37, v22);
  EVENT_LOG::EventDataDescCreate_UnicodeString(v20, &v38, v23);
  CPushEtwActivityId::CPushEtwActivityId((CPushEtwActivityId *)v24, a6);
  v16 = EtwEventWrite(*(_QWORD *)v12, &EVT_INCORRECT_HTTP_REPLY, 10, &v25);
  if ( v16 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids, 202, v16);
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    EtwEventActivityIdControl(2, v24);
  }
  else
  {
    EtwEventActivityIdControl(2, v24);
    v16 = 0;
  }
LABEL_15:
  GenericStringHandle<unsigned short>::FreeIt(a2);
  SidHandle::~SidHandle((SidHandle *)a3);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800b5b34  mov     [rsp-8+arg_0], rbx
0x1800b5b39  push    rbp
0x1800b5b3a  push    rsi
0x1800b5b3b  push    rdi
0x1800b5b3c  push    r12
0x1800b5b3e  push    r13
0x1800b5b40  push    r14
0x1800b5b42  push    r15
0x1800b5b44  lea     rbp, [rsp-7]
0x1800b5b49  sub     rsp, 100h
0x1800b5b50  mov     rax, cs:__security_cookie
0x1800b5b57  xor     rax, rsp
0x1800b5b5a  mov     [rbp+37h+var_40], rax
0x1800b5b5e  mov     rax, [rbp+37h+arg_48]
0x1800b5b65  mov     r15, r9
0x1800b5b68  mov     rbx, cs:?g_EventLogger@@3PEAVEVENT_LOG@@EA; EVENT_LOG * g_EventLogger
0x1800b5b6f  mov     rdi, r8
0x1800b5b72  mov     r12, [rbp+37h+arg_20]
0x1800b5b76  mov     rsi, rdx
0x1800b5b79  mov     r14, [rbp+37h+arg_28]
0x1800b5b7d  mov     r13, [rbp+37h+arg_30]
0x1800b5b81  cmp     qword ptr [rbx], 0
0x1800b5b85  mov     [rsp+130h+var_100], rax
0x1800b5b8a  mov     rax, [rbp+37h+arg_50]
0x1800b5b91  mov     [rsp+130h+var_F8], rax
0x1800b5b96  jnz     short loc_1800B5BC8
0x1800b5b98  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5b9f  lea     rax, WPP_GLOBAL_Control
0x1800b5ba6  cmp     rcx, rax
0x1800b5ba9  jz      short loc_1800B5BE8
0x1800b5bab  test    byte ptr [rcx+1Ch], 1
0x1800b5baf  jz      short loc_1800B5BE8
0x1800b5bb1  mov     rcx, [rcx+10h]
0x1800b5bb5  lea     r8, WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids
0x1800b5bbc  mov     edx, 28h ; '('
0x1800b5bc1  call    WPP_SF_
0x1800b5bc6  jmp     short loc_1800B5BE8
0x1800b5bc8  mov     rdx, [rbx+8]; lpBuffer
0x1800b5bcc  mov     rcx, [r8]; Sid
0x1800b5bcf  call    ?SidToUser@EVENT_LOG@@SAJPEAXPEAG_K@Z; EVENT_LOG::SidToUser(void *,ushort *,unsigned __int64)
0x1800b5bd4  mov     rcx, [rbx]
0x1800b5bd7  lea     rdx, EVT_INCORRECT_HTTP_REPLY
0x1800b5bde  call    cs:__imp_EtwEventEnabled
0x1800b5be4  test    al, al
0x1800b5be6  jnz     short loc_1800B5BEF
0x1800b5be8  xor     ebx, ebx
0x1800b5bea  jmp     loc_1800B5D17
0x1800b5bef  mov     r8, [rsi]
0x1800b5bf2  lea     rdx, [rsp+130h+var_E0]; struct _EVENT_DATA_DESCRIPTOR *
0x1800b5bf7  add     r8, 0Ch; unsigned __int16 *
0x1800b5bfb  call    ?EventDataDescCreate_UnicodeString@EVENT_LOG@@IEAAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; EVENT_LOG::EventDataDescCreate_UnicodeString(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800b5c00  mov     r8, [rbx+8]; unsigned __int16 *
0x1800b5c04  lea     rdx, [rsp+130h+var_D0]; struct _EVENT_DATA_DESCRIPTOR *
0x1800b5c09  call    ?EventDataDescCreate_UnicodeString@EVENT_LOG@@IEAAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; EVENT_LOG::EventDataDescCreate_UnicodeString(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800b5c0e  mov     [rsp+130h+var_C0], r15
0x1800b5c13  lea     rdx, [rbp+37h+var_B0]; struct _EVENT_DATA_DESCRIPTOR *
0x1800b5c17  mov     r8, r12; unsigned __int16 *
0x1800b5c1a  mov     [rsp+130h+var_B8], 10h
0x1800b5c23  xor     r15d, r15d
0x1800b5c26  call    ?EventDataDescCreate_UnicodeString@EVENT_LOG@@IEAAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; EVENT_LOG::EventDataDescCreate_UnicodeString(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800b5c2b  mov     r8, r13; unsigned __int16 *
0x1800b5c2e  mov     [rbp+37h+var_A0], r14
0x1800b5c32  lea     rdx, [rbp+37h+var_90]; struct _EVENT_DATA_DESCRIPTOR *
0x1800b5c36  mov     [rbp+37h+var_98], 10h
0x1800b5c3e  call    ?EventDataDescCreate_UnicodeString@EVENT_LOG@@IEAAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; EVENT_LOG::EventDataDescCreate_UnicodeString(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800b5c43  mov     r8, [rsp+130h+var_100]; unsigned __int16 *
0x1800b5c48  lea     rax, [rbp+37h+arg_40]
0x1800b5c4f  lea     rcx, [rbp+37h+arg_38]; this
0x1800b5c53  mov     [rbp+37h+var_70], rax
0x1800b5c57  lea     rdx, [rbp+37h+var_60]; struct _EVENT_DATA_DESCRIPTOR *
0x1800b5c5b  mov     [rbp+37h+var_80], rcx
0x1800b5c5f  mov     [rbp+37h+var_78], 4
0x1800b5c67  mov     [rbp+37h+var_68], 8
0x1800b5c6f  call    ?EventDataDescCreate_UnicodeString@EVENT_LOG@@IEAAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; EVENT_LOG::EventDataDescCreate_UnicodeString(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800b5c74  mov     r8, [rsp+130h+var_F8]; unsigned __int16 *
0x1800b5c79  lea     rdx, [rbp+37h+var_50]; struct _EVENT_DATA_DESCRIPTOR *
0x1800b5c7d  call    ?EventDataDescCreate_UnicodeString@EVENT_LOG@@IEAAXPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; EVENT_LOG::EventDataDescCreate_UnicodeString(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800b5c82  mov     rdx, r14; struct _GUID *
0x1800b5c85  lea     rcx, [rsp+130h+var_F0]; this
0x1800b5c8a  call    ??0CPushEtwActivityId@@QEAA@AEBU_GUID@@@Z; CPushEtwActivityId::CPushEtwActivityId(_GUID const &)
0x1800b5c8f  mov     rcx, [rbx]
0x1800b5c92  lea     r9, [rsp+130h+var_E0]
0x1800b5c97  lea     r8d, [r15+0Ah]
0x1800b5c9b  lea     rdx, EVT_INCORRECT_HTTP_REPLY
0x1800b5ca2  call    cs:__imp_EtwEventWrite
0x1800b5ca8  mov     ebx, eax
0x1800b5caa  test    eax, eax
0x1800b5cac  jz      short loc_1800B5D04
0x1800b5cae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5cb5  lea     rax, WPP_GLOBAL_Control
0x1800b5cbc  cmp     rcx, rax
0x1800b5cbf  jz      short loc_1800B5CE5
0x1800b5cc1  test    byte ptr [rcx+1Ch], 4
0x1800b5cc5  jz      short loc_1800B5CE5
0x1800b5cc7  mov     rcx, [rcx+10h]
0x1800b5ccb  lea     edx, [r15+29h]
0x1800b5ccf  mov     r9d, 0CAh
0x1800b5cd5  mov     [rsp+130h+var_110], ebx
0x1800b5cd9  lea     r8, WPP_a0077a5cd3783f3e8e23f6b4cfc88fd0_Traceguids
0x1800b5ce0  call    WPP_SF_Dd
0x1800b5ce5  test    ebx, ebx
0x1800b5ce7  jle     short loc_1800B5CF2
0x1800b5ce9  movzx   ebx, bx
0x1800b5cec  or      ebx, 80070000h
0x1800b5cf2  lea     rdx, [rsp+130h+var_F0]
0x1800b5cf7  mov     ecx, 2
0x1800b5cfc  call    cs:__imp_EtwEventActivityIdControl
0x1800b5d02  jmp     short loc_1800B5D17
0x1800b5d04  lea     rdx, [rsp+130h+var_F0]
0x1800b5d09  mov     ecx, 2
0x1800b5d0e  call    cs:__imp_EtwEventActivityIdControl
0x1800b5d14  mov     ebx, r15d
0x1800b5d17  mov     rcx, rsi
0x1800b5d1a  call    ?FreeIt@?$GenericStringHandle@G@@AEAAXXZ; GenericStringHandle<ushort>::FreeIt(void)
0x1800b5d1f  mov     rcx, rdi; this
0x1800b5d22  call    ??1SidHandle@@QEAA@XZ; SidHandle::~SidHandle(void)
0x1800b5d27  mov     eax, ebx
0x1800b5d29  mov     rcx, [rbp+37h+var_40]
0x1800b5d2d  xor     rcx, rsp; StackCookie
0x1800b5d30  call    __security_check_cookie
0x1800b5d35  mov     rbx, [rsp+130h+arg_0]
0x1800b5d3d  add     rsp, 100h
0x1800b5d44  pop     r15
0x1800b5d46  pop     r14
0x1800b5d48  pop     r13
0x1800b5d4a  pop     r12
0x1800b5d4c  pop     rdi
0x1800b5d4d  pop     rsi
0x1800b5d4e  pop     rbp
0x1800b5d4f  retn
```
