# KAMSS_MeasurementUpdateCallback

- ea: `0x1800025c0`
- end: `0x1800026ff`
- name: `KAMSS_MeasurementUpdateCallback`
- size: `319`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180001e20`
- `0x1800025c0`
- `0x1800032c0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000264a`
- `RPCRT4!NdrClientCall3` at `0x18000264a`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall KAMSS_MeasurementUpdateCallback(_QWORD *a1, __int64 a2)
{
  CLIENT_CALL_RETURN result; // rax
  CLIENT_CALL_RETURN v5; // r8
  _QWORD *v6; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
  }
  result.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, *a1, a1[1], a1[25], a1[26], a2).Pointer;
  if ( !LODWORD(result.Pointer) )
    goto LABEL_10;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    result.Simple = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_D)(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      30,
                      (CLIENT_CALL_RETURN)v5.Simple,
                      LODWORD(result.Pointer));
LABEL_10:
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 6u )
    return (CLIENT_CALL_RETURN)WPP_SF_(v6[2], 32, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800025c0  mov     [rsp+arg_8], rbx
0x1800025c5  mov     [rsp+arg_10], rsi
0x1800025ca  push    rdi
0x1800025cb  sub     rsp, 40h
0x1800025cf  mov     rsi, rdx
0x1800025d2  mov     rdi, rcx
0x1800025d5  lea     rbx, WPP_GLOBAL_Control
0x1800025dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800025e3  cmp     rcx, rbx
0x1800025e6  jz      short loc_18000260A
0x1800025e8  test    byte ptr [rcx+1Ch], 1
0x1800025ec  jz      short loc_18000260A
0x1800025ee  cmp     byte ptr [rcx+19h], 6
0x1800025f2  jb      short loc_18000260A
0x1800025f4  mov     edx, 1Dh
0x1800025f9  lea     r8, WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids
0x180002600  mov     rcx, [rcx+10h]
0x180002604  call    WPP_SF_
0x180002609  nop
0x18000260a  mov     rax, [rdi+0D0h]
0x180002611  mov     rcx, [rdi+0C8h]
0x180002618  mov     rdx, [rdi+8]
0x18000261c  mov     [rsp+48h+arg_0], 0
0x180002625  mov     [rsp+48h+var_10], rsi
0x18000262a  mov     [rsp+48h+var_18], rax
0x18000262f  mov     [rsp+48h+var_20], rcx
0x180002634  mov     [rsp+48h+var_28], rdx
0x180002639  mov     r9, [rdi]
0x18000263c  xor     r8d, r8d; pReturnValue
0x18000263f  lea     edx, [r8+2]; nProcNum
0x180002643  lea     rcx, pProxyInfo; pProxyInfo
0x18000264a  call    cs:__imp_NdrClientCall3
0x180002650  mov     [rsp+48h+arg_0], rax
0x180002655  test    eax, eax
0x180002657  jz      short loc_180002682
0x180002659  mov     rcx, cs:WPP_GLOBAL_Control
0x180002660  cmp     rcx, rbx
0x180002663  jz      short loc_180002689
0x180002665  test    byte ptr [rcx+1Ch], 1
0x180002669  jz      short loc_180002689
0x18000266b  cmp     byte ptr [rcx+19h], 2
0x18000266f  jb      short loc_180002689
0x180002671  mov     edx, 1Eh
0x180002676  mov     r9d, eax
0x180002679  mov     rcx, [rcx+10h]
0x18000267d  call    WPP_SF_D
0x180002682  mov     rcx, cs:WPP_GLOBAL_Control
0x180002689  jmp     short loc_1800026C9
0x18000268b  lea     rdx, WPP_GLOBAL_Control
0x180002692  mov     rcx, cs:WPP_GLOBAL_Control
0x180002699  cmp     rcx, rdx
0x18000269c  jz      short loc_1800026C2
0x18000269e  test    byte ptr [rcx+1Ch], 1
0x1800026a2  jz      short loc_1800026C2
0x1800026a4  cmp     byte ptr [rcx+19h], 2
0x1800026a8  jb      short loc_1800026C2
0x1800026aa  mov     r9d, eax
0x1800026ad  mov     edx, 1Fh
0x1800026b2  mov     rcx, [rcx+10h]
0x1800026b6  call    WPP_SF_D
0x1800026bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026c2  lea     rbx, WPP_GLOBAL_Control
0x1800026c9  cmp     rcx, rbx
0x1800026cc  jz      short loc_1800026EF
0x1800026ce  test    byte ptr [rcx+1Ch], 1
0x1800026d2  jz      short loc_1800026EF
0x1800026d4  cmp     byte ptr [rcx+19h], 6
0x1800026d8  jb      short loc_1800026EF
0x1800026da  mov     edx, 20h ; ' '
0x1800026df  lea     r8, WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids
0x1800026e6  mov     rcx, [rcx+10h]
0x1800026ea  call    WPP_SF_
0x1800026ef  mov     rbx, [rsp+48h+arg_8]
0x1800026f4  mov     rsi, [rsp+48h+arg_10]
0x1800026f9  add     rsp, 40h
0x1800026fd  pop     rdi
0x1800026fe  retn
```
