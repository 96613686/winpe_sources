# PpfhLogEventFirmwareUpdateFveRpcrpInit(uint,ushort const *,ushort const *,ushort const *)

- ea: `0x180035440`
- end: `0x18003554f`
- name: `?PpfhLogEventFirmwareUpdateFveRpcrpInit@@YAJIPEBG00@Z`
- size: `271`
- prototype: `int __fastcall(unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18004fe98`

## callees

- `0x180003270`
- `0x180003cf0`
- `0x180009c64`
- `0x18000dfe0`
- `0x18003535c`
- `0x180035440`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180035509`
- `ntdll!EtwEventWrite` at `0x180035509`

## pseudocode

```c
int __fastcall PpfhLogEventFirmwareUpdateFveRpcrpInit(
        unsigned int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v7; // ebx
  __int64 v8; // rdx
  unsigned int v10; // eax
  unsigned int v11[2]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v12; // [rsp+28h] [rbp-60h]
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+40h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  unsigned int v17; // [rsp+90h] [rbp+8h] BYREF

  v17 = a1;
  memset_0(v11, 0, 0x40u);
  v12 = 4;
  *(_QWORD *)v11 = &v17;
  v7 = InitializeEventDataDescWithStr(&v13, a2);
  if ( v7 < 0 )
  {
    v8 = 419;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
      (const char *)(unsigned int)v7,
      v11[0]);
    return v7;
  }
  v7 = InitializeEventDataDescWithStr(&v14, a3);
  if ( v7 < 0 )
  {
    v8 = 420;
    goto LABEL_3;
  }
  v7 = InitializeEventDataDescWithStr(&v15, a4);
  if ( v7 < 0 )
  {
    v8 = 421;
    goto LABEL_3;
  }
  v10 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_FIRMWARE_UPDATE_FVE_RPCRP_INIT, 4, v11);
  if ( v10 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1A7,
             (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
             (const char *)v10,
             v11[0]);
  else
    return 0;
}

```

## disassembly

```asm
0x180035440  mov     [rsp+arg_0], ecx
0x180035444  push    rbx
0x180035445  push    rsi
0x180035446  push    rdi
0x180035447  sub     rsp, 70h
0x18003544b  mov     rax, cs:__security_cookie
0x180035452  xor     rax, rsp
0x180035455  mov     [rsp+88h+var_28], rax
0x18003545a  mov     rbx, rdx
0x18003545d  lea     rcx, [rsp+88h+var_68]; void *
0x180035462  xor     edx, edx; Val
0x180035464  mov     rdi, r8
0x180035467  mov     rsi, r9
0x18003546a  lea     r8d, [rdx+40h]; Size
0x18003546e  call    memset_0
0x180035473  lea     rax, [rsp+88h+arg_0]
0x18003547b  mov     [rsp+88h+var_60], 4
0x180035484  mov     rdx, rbx; unsigned __int16 *
0x180035487  mov     qword ptr [rsp+88h+var_68], rax; unsigned int
0x18003548c  lea     rcx, [rsp+88h+var_58]; struct _EVENT_DATA_DESCRIPTOR *
0x180035491  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180035496  mov     ebx, eax
0x180035498  test    eax, eax
0x18003549a  jns     short loc_1800354BC
0x18003549c  mov     edx, 1A3h; void *
0x1800354a1  mov     rcx, [rsp+88h]; this
0x1800354a9  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800354b0  mov     r9d, ebx; char *
0x1800354b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800354b8  mov     eax, ebx
0x1800354ba  jmp     short loc_180035539
0x1800354bc  mov     rdx, rdi; unsigned __int16 *
0x1800354bf  lea     rcx, [rsp+88h+var_48]; struct _EVENT_DATA_DESCRIPTOR *
0x1800354c4  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800354c9  mov     ebx, eax
0x1800354cb  test    eax, eax
0x1800354cd  jns     short loc_1800354D6
0x1800354cf  mov     edx, 1A4h
0x1800354d4  jmp     short loc_1800354A1
0x1800354d6  mov     rdx, rsi; unsigned __int16 *
0x1800354d9  lea     rcx, [rsp+88h+var_38]; struct _EVENT_DATA_DESCRIPTOR *
0x1800354de  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800354e3  mov     ebx, eax
0x1800354e5  test    eax, eax
0x1800354e7  jns     short loc_1800354F0
0x1800354e9  mov     edx, 1A5h
0x1800354ee  jmp     short loc_1800354A1
0x1800354f0  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x1800354f7  lea     r9, [rsp+88h+var_68]
0x1800354fc  mov     r8d, 4
0x180035502  lea     rdx, PCRPF_EVENT_FIRMWARE_UPDATE_FVE_RPCRP_INIT
0x180035509  call    cs:__imp_EtwEventWrite
0x180035510  nop     dword ptr [rax+rax+00h]
0x180035515  test    eax, eax
0x180035517  jz      short loc_180035537
0x180035519  mov     rcx, [rsp+88h]; this
0x180035521  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035528  mov     r9d, eax; char *
0x18003552b  mov     edx, 1A7h; void *
0x180035530  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035535  jmp     short loc_180035539
0x180035537  xor     eax, eax
0x180035539  mov     rcx, [rsp+88h+var_28]
0x18003553e  xor     rcx, rsp; StackCookie
0x180035541  call    __security_check_cookie
0x180035546  add     rsp, 70h
0x18003554a  pop     rdi
0x18003554b  pop     rsi
0x18003554c  pop     rbx
0x18003554d  retn
```
