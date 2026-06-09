# RTpCheckComputerProps(tagMQPRIVATEPROPS *,long *)

- ea: `0x18000c4ec`
- end: `0x18000c5eb`
- name: `?RTpCheckComputerProps@@YAJPEAUtagMQPRIVATEPROPS@@PEAJ@Z`
- size: `255`
- prototype: `__int64 __fastcall(struct tagMQPRIVATEPROPS *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a120`

## callees

- `0x180005488`
- `0x18000a33c`
- `0x18000b080`
- `0x18000c4ec`
- `0x180013c74`

## pseudocode

```c
__int64 __fastcall RTpCheckComputerProps(struct tagMQPRIVATEPROPS *a1, int *a2)
{
  int v2; // eax
  unsigned int v3; // ebx

  if ( !a1 || !a1->cProp )
    return LogHR(-1072824197, (wchar_t *)L"rt/property", 0x2BCu);
  v2 = CheckProps(
         a1->cProp,
         a1->aPropID,
         a1->aPropVar,
         (_DWORD)a2,
         5800,
         5802,
         (__int64)&GetPrivateComputerValidation,
         (__int64)&GetPrivateComputerVarTypes,
         1,
         0,
         0);
  v3 = v2;
  if ( v2 < 0 )
    LogMsgHR(v2, (wchar_t *)L"rt/property", 0x2D0u);
  return v3;
}

```

## disassembly

```asm
0x18000c4ec  push    rbx
0x18000c4ee  sub     rsp, 70h
0x18000c4f2  test    rcx, rcx
0x18000c4f5  jz      short loc_18000C557
0x18000c4f7  cmp     dword ptr [rcx], 0
0x18000c4fa  jz      short loc_18000C557
0x18000c4fc  mov     [rsp+78h+var_28], 0
0x18000c505  mov     [rsp+78h+var_30], 0
0x18000c50d  mov     [rsp+78h+var_38], 1
0x18000c515  lea     rax, ?GetPrivateComputerVarTypes@@3PAGA; ushort near * GetPrivateComputerVarTypes
0x18000c51c  mov     [rsp+78h+var_40], rax
0x18000c521  lea     rax, ?GetPrivateComputerValidation@@3PAUpropValidity@@A; propValidity near * GetPrivateComputerValidation
0x18000c528  mov     [rsp+78h+var_48], rax
0x18000c52d  mov     [rsp+78h+var_50], 16AAh
0x18000c535  mov     [rsp+78h+var_58], 16A8h
0x18000c53d  mov     r9, rdx
0x18000c540  mov     r8, [rcx+10h]
0x18000c544  mov     rdx, [rcx+8]
0x18000c548  mov     ecx, [rcx]
0x18000c54a  call    CheckProps
0x18000c54f  mov     ebx, eax
0x18000c551  mov     [rsp+78h+var_18], eax
0x18000c555  jmp     short loc_18000C5CB
0x18000c557  mov     r8d, 2BCh; unsigned __int16
0x18000c55d  lea     rdx, aRtProperty; "rt/property"
0x18000c564  mov     ecx, 0C00E007Bh; int
0x18000c569  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18000c56e  jmp     short loc_18000C5E5
0x18000c570  mov     ebx, eax
0x18000c572  lea     rax, WPP_GLOBAL_Control
0x18000c579  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c580  cmp     rcx, rax
0x18000c583  jz      short loc_18000C5A0
0x18000c585  test    byte ptr [rcx+1Ch], 1
0x18000c589  jz      short loc_18000C5A0
0x18000c58b  mov     edx, 13h
0x18000c590  lea     r8, WPP_12aee58279bf3ca20cf3faeeae7b8b10_Traceguids
0x18000c597  mov     rcx, [rcx+10h]
0x18000c59b  call    WPP_SF_
0x18000c5a0  test    ebx, ebx
0x18000c5a2  jg      short loc_18000C5A8
0x18000c5a4  mov     ecx, ebx
0x18000c5a6  jmp     short loc_18000C5B1
0x18000c5a8  movzx   ecx, bx
0x18000c5ab  or      ecx, 80070000h; int
0x18000c5b1  test    ecx, ecx
0x18000c5b3  jns     short loc_18000C5C7
0x18000c5b5  mov     r8d, 2C6h; unsigned __int16
0x18000c5bb  lea     rdx, aRtProperty; "rt/property"
0x18000c5c2  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000c5c7  mov     [rsp+78h+var_18], ebx
0x18000c5cb  test    ebx, ebx
0x18000c5cd  jns     short loc_18000C5E3
0x18000c5cf  mov     r8d, 2D0h; unsigned __int16
0x18000c5d5  lea     rdx, aRtProperty; "rt/property"
0x18000c5dc  mov     ecx, ebx; int
0x18000c5de  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18000c5e3  mov     eax, ebx
0x18000c5e5  add     rsp, 70h
0x18000c5e9  pop     rbx
0x18000c5ea  retn
```
