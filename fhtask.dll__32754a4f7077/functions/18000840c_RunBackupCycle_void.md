# RunBackupCycle(void)

- ea: `0x18000840c`
- end: `0x1800084ad`
- name: `?RunBackupCycle@@YAJXZ`
- size: `161`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180007ba0`

## callees

- `0x1800067a0`
- `0x18000840c`

## import_xrefs

- `fhsvcctl!FhServiceStartBackup` at `0x180008458`
- `fhsvcctl!FhServiceStartBackup` at `0x180008458`
- `fhsvcctl!FhServiceOpenPipe` at `0x180008425`
- `fhsvcctl!FhServiceOpenPipe` at `0x180008425`
- `fhsvcctl!FhServiceClosePipe` at `0x18000849f`
- `fhsvcctl!FhServiceClosePipe` at `0x18000849f`

## pseudocode

```c
__int64 RunBackupCycle(void)
{
  int started; // ebx
  _QWORD *v1; // rcx
  __int64 v2; // rdx
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  started = FhServiceOpenPipe(1, &v4);
  if ( started >= 0 )
  {
    started = FhServiceStartBackup(v4, 0);
    if ( started < 0 )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v2 = 36;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v2 = 35;
LABEL_9:
      WPP_SF_d(v1[2], v2, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids, (unsigned int)started);
    }
  }
  if ( v4 )
    FhServiceClosePipe();
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18000840c  push    rbx
0x18000840e  sub     rsp, 20h
0x180008412  lea     rdx, [rsp+28h+arg_0]
0x180008417  mov     [rsp+28h+arg_0], 0
0x180008420  mov     ecx, 1
0x180008425  call    cs:__imp_FhServiceOpenPipe
0x18000842b  mov     ebx, eax
0x18000842d  test    eax, eax
0x18000842f  jns     short loc_180008451
0x180008431  mov     rcx, cs:WPP_GLOBAL_Control
0x180008438  lea     rax, WPP_GLOBAL_Control
0x18000843f  cmp     rcx, rax
0x180008442  jz      short loc_180008495
0x180008444  test    byte ptr [rcx+1Ch], 1
0x180008448  jz      short loc_180008495
0x18000844a  mov     edx, 23h ; '#'
0x18000844f  jmp     short loc_180008482
0x180008451  mov     rcx, [rsp+28h+arg_0]
0x180008456  xor     edx, edx
0x180008458  call    cs:__imp_FhServiceStartBackup
0x18000845e  mov     ebx, eax
0x180008460  test    eax, eax
0x180008462  jns     short loc_180008495
0x180008464  mov     rcx, cs:WPP_GLOBAL_Control
0x18000846b  lea     rax, WPP_GLOBAL_Control
0x180008472  cmp     rcx, rax
0x180008475  jz      short loc_180008495
0x180008477  test    byte ptr [rcx+1Ch], 1
0x18000847b  jz      short loc_180008495
0x18000847d  mov     edx, 24h ; '$'
0x180008482  mov     rcx, [rcx+10h]
0x180008486  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x18000848d  mov     r9d, ebx
0x180008490  call    WPP_SF_d
0x180008495  mov     rcx, [rsp+28h+arg_0]
0x18000849a  test    rcx, rcx
0x18000849d  jz      short loc_1800084A5
0x18000849f  call    cs:__imp_FhServiceClosePipe
0x1800084a5  mov     eax, ebx
0x1800084a7  add     rsp, 20h
0x1800084ab  pop     rbx
0x1800084ac  retn
```
