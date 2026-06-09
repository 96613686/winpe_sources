# IsDisplayInMuxPair(ushort const *)

- ea: `0x180029404`
- end: `0x180029502`
- name: `?IsDisplayInMuxPair@@YA_NPEBG@Z`
- size: `254`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004da68`

## callees

- `0x18001582c`
- `0x180029404`
- `0x18002e5f0`
- `0x18002f2f4`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x180029479`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x180029479`

## pseudocode

```c
bool __fastcall IsDisplayInMuxPair(const unsigned __int16 *a1)
{
  bool result; // al
  struct DISPLAYCONFIG_PATH_INFO v3; // [rsp+20h] [rbp-E0h] BYREF
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v5[89]; // [rsp+A8h] [rbp-58h]
  _DWORD v6[93]; // [rsp+20Ch] [rbp+10Ch]

  memset_0(&v3, 0, sizeof(v3));
  result = (int)InternalTranslateICMNameToPath(a1, &v3) >= 0
        && (memset_0(&requestPacket.adapterId, 0, 0x300u),
            requestPacket.type = -34,
            requestPacket.size = 776,
            DisplayConfigGetDeviceInfo(&requestPacket) >= 0)
        && (*(_QWORD *)&v6[1] == *(_QWORD *)&v3.targetInfo.adapterId && v6[86] == v3.targetInfo.id
         || *(_QWORD *)&v5[1] == *(_QWORD *)&v3.targetInfo.adapterId && v5[86] == v3.targetInfo.id);
  return result;
}

```

## disassembly

```asm
0x180029404  mov     [rsp-8+arg_8], rbx
0x180029409  push    rbp
0x18002940a  lea     rbp, [rsp-290h]
0x180029412  sub     rsp, 390h
0x180029419  mov     rax, cs:__security_cookie
0x180029420  xor     rax, rsp
0x180029423  mov     [rbp+290h+var_10], rax
0x18002942a  xor     edx, edx; Val
0x18002942c  mov     rbx, rcx
0x18002942f  lea     rcx, [rsp+390h+var_370]; void *
0x180029434  lea     r8d, [rdx+48h]; Size
0x180029438  call    memset_0
0x18002943d  lea     rdx, [rsp+390h+var_370]; struct DISPLAYCONFIG_PATH_INFO *
0x180029442  mov     rcx, rbx; unsigned __int16 *
0x180029445  call    ?InternalTranslateICMNameToPath@@YAJPEBGPEAUDISPLAYCONFIG_PATH_INFO@@@Z; InternalTranslateICMNameToPath(ushort const *,DISPLAYCONFIG_PATH_INFO *)
0x18002944a  test    eax, eax
0x18002944c  js      loc_1800294E0
0x180029452  xor     edx, edx; Val
0x180029454  lea     rcx, [rsp+390h+requestPacket.adapterId]; void *
0x180029459  mov     r8d, 300h; Size
0x18002945f  call    memset_0
0x180029464  lea     rcx, [rsp+390h+requestPacket]; requestPacket
0x180029469  mov     [rsp+390h+requestPacket.type], 0FFFFFFDEh
0x180029471  mov     [rsp+390h+requestPacket.size], 308h
0x180029479  call    cs:__imp_DisplayConfigGetDeviceInfo
0x18002947f  test    eax, eax
0x180029481  js      short loc_1800294E0
0x180029483  mov     rdx, qword ptr [rsp+390h+var_370.targetInfo.adapterId.HighPart]
0x180029488  mov     r8, qword ptr [rsp+390h+var_370.sourceInfo.statusFlags]
0x18002948d  cmp     dword ptr [rbp+290h+var_184+8], edx
0x180029493  jnz     short loc_1800294BA
0x180029495  mov     rax, qword ptr [rbp+290h+var_184]
0x18002949c  mov     rcx, r8
0x18002949f  shr     rcx, 20h
0x1800294a3  shr     rax, 20h
0x1800294a7  cmp     eax, ecx
0x1800294a9  jnz     short loc_1800294BA
0x1800294ab  mov     rax, rdx
0x1800294ae  shr     rax, 20h
0x1800294b2  cmp     [rbp+290h+var_2C], eax
0x1800294b8  jz      short loc_1800294DC
0x1800294ba  cmp     dword ptr [rbp+290h+var_2E8+8], edx
0x1800294bd  jnz     short loc_1800294E0
0x1800294bf  mov     rax, qword ptr [rbp+290h+var_2E8]
0x1800294c3  shr     rax, 20h
0x1800294c7  shr     r8, 20h
0x1800294cb  cmp     eax, r8d
0x1800294ce  jnz     short loc_1800294E0
0x1800294d0  shr     rdx, 20h
0x1800294d4  cmp     [rbp+290h+var_190], edx
0x1800294da  jnz     short loc_1800294E0
0x1800294dc  mov     al, 1
0x1800294de  jmp     short loc_1800294E2
0x1800294e0  xor     al, al
0x1800294e2  mov     rcx, [rbp+290h+var_10]
0x1800294e9  xor     rcx, rsp; StackCookie
0x1800294ec  call    __security_check_cookie
0x1800294f1  mov     rbx, [rsp+390h+arg_8]
0x1800294f9  add     rsp, 390h
0x180029500  pop     rbp
0x180029501  retn
```
