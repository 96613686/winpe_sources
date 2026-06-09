# PpfhLogEventFirmwareUpdateTransformStaged(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180035558`
- end: `0x180035670`
- name: `?PpfhLogEventFirmwareUpdateTransformStaged@@YAJPEBG000@Z`
- size: `280`
- prototype: `int __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
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
- `0x180035558`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180035629`
- `ntdll!EtwEventWrite` at `0x180035629`

## pseudocode

```c
int __fastcall PpfhLogEventFirmwareUpdateTransformStaged(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v8; // ebx
  __int64 v9; // rdx
  unsigned int v11; // eax
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+20h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+30h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+40h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  memset_0(&v12, 0, 0x40u);
  v8 = InitializeEventDataDescWithStr(&v12, a1);
  if ( v8 < 0 )
  {
    v9 = 400;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
      (const char *)(unsigned int)v8,
      v12.Ptr);
    return v8;
  }
  v8 = InitializeEventDataDescWithStr(&v13, a2);
  if ( v8 < 0 )
  {
    v9 = 401;
    goto LABEL_3;
  }
  v8 = InitializeEventDataDescWithStr(&v14, a3);
  if ( v8 < 0 )
  {
    v9 = 402;
    goto LABEL_3;
  }
  v8 = InitializeEventDataDescWithStr(&v15, a4);
  if ( v8 < 0 )
  {
    v9 = 403;
    goto LABEL_3;
  }
  v11 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_FIRMWARE_UPDATE_TRANSFORM_STAGED, 4, &v12);
  if ( v11 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x195,
             (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
             (const char *)v11,
             v12.Ptr);
  else
    return 0;
}

```

## disassembly

```asm
0x180035558  push    rbx
0x18003555a  push    rbp
0x18003555b  push    rsi
0x18003555c  push    rdi
0x18003555d  sub     rsp, 78h
0x180035561  mov     rax, cs:__security_cookie
0x180035568  xor     rax, rsp
0x18003556b  mov     [rsp+98h+var_38], rax
0x180035570  mov     rsi, rdx
0x180035573  mov     rbp, r8
0x180035576  xor     edx, edx; Val
0x180035578  mov     rbx, rcx
0x18003557b  lea     rcx, [rsp+98h+var_78]; void *
0x180035580  mov     rdi, r9
0x180035583  lea     r8d, [rdx+40h]; Size
0x180035587  call    memset_0
0x18003558c  mov     rdx, rbx; unsigned __int16 *
0x18003558f  lea     rcx, [rsp+98h+var_78]; struct _EVENT_DATA_DESCRIPTOR *
0x180035594  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180035599  mov     ebx, eax
0x18003559b  test    eax, eax
0x18003559d  jns     short loc_1800355C2
0x18003559f  mov     edx, 190h; void *
0x1800355a4  mov     rcx, [rsp+98h]; this
0x1800355ac  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800355b3  mov     r9d, ebx; char *
0x1800355b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800355bb  mov     eax, ebx
0x1800355bd  jmp     loc_180035659
0x1800355c2  mov     rdx, rsi; unsigned __int16 *
0x1800355c5  lea     rcx, [rsp+98h+var_68]; struct _EVENT_DATA_DESCRIPTOR *
0x1800355ca  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800355cf  mov     ebx, eax
0x1800355d1  test    eax, eax
0x1800355d3  jns     short loc_1800355DC
0x1800355d5  mov     edx, 191h
0x1800355da  jmp     short loc_1800355A4
0x1800355dc  mov     rdx, rbp; unsigned __int16 *
0x1800355df  lea     rcx, [rsp+98h+var_58]; struct _EVENT_DATA_DESCRIPTOR *
0x1800355e4  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x1800355e9  mov     ebx, eax
0x1800355eb  test    eax, eax
0x1800355ed  jns     short loc_1800355F6
0x1800355ef  mov     edx, 192h
0x1800355f4  jmp     short loc_1800355A4
0x1800355f6  mov     rdx, rdi; unsigned __int16 *
0x1800355f9  lea     rcx, [rsp+98h+var_48]; struct _EVENT_DATA_DESCRIPTOR *
0x1800355fe  call    ?InitializeEventDataDescWithStr@@YAJPEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; InitializeEventDataDescWithStr(_EVENT_DATA_DESCRIPTOR *,ushort const *)
0x180035603  mov     ebx, eax
0x180035605  test    eax, eax
0x180035607  jns     short loc_180035610
0x180035609  mov     edx, 193h
0x18003560e  jmp     short loc_1800355A4
0x180035610  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x180035617  lea     r9, [rsp+98h+var_78]
0x18003561c  mov     r8d, 4
0x180035622  lea     rdx, PCRPF_EVENT_FIRMWARE_UPDATE_TRANSFORM_STAGED
0x180035629  call    cs:__imp_EtwEventWrite
0x180035630  nop     dword ptr [rax+rax+00h]
0x180035635  test    eax, eax
0x180035637  jz      short loc_180035657
0x180035639  mov     rcx, [rsp+98h]; this
0x180035641  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180035648  mov     r9d, eax; char *
0x18003564b  mov     edx, 195h; void *
0x180035650  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035655  jmp     short loc_180035659
0x180035657  xor     eax, eax
0x180035659  mov     rcx, [rsp+98h+var_38]
0x18003565e  xor     rcx, rsp; StackCookie
0x180035661  call    __security_check_cookie
0x180035666  add     rsp, 78h
0x18003566a  pop     rdi
0x18003566b  pop     rsi
0x18003566c  pop     rbp
0x18003566d  pop     rbx
0x18003566e  retn
```
