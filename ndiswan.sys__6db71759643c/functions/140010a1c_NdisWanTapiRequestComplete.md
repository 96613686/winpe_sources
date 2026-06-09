# NdisWanTapiRequestComplete

- ea: `0x140010a1c`
- end: `0x140010b2b`
- name: `NdisWanTapiRequestComplete`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000fe00`

## callees

- `0x14000a290`
- `0x14000a2c0`
- `0x14000a5f4`
- `0x140010a1c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140010b14`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140010b14`
- `NDISTAPI!NdisTapiCompleteRequest` at `0x140010afe`
- `NDISTAPI!NdisTapiCompleteRequest` at `0x140010afe`

## pseudocode

```c
void __fastcall NdisWanTapiRequestComplete(__int64 a1, __int64 a2)
{
  unsigned int *v4; // rdi
  __int64 v5; // r9

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_19c4b30392dd32e174279c73e079de55_Traceguids);
  }
  v4 = *(unsigned int **)(a2 + 224);
  v5 = v4[8];
  if ( (unsigned int)v5 <= 1 )
    v4[15] = *(_DWORD *)(a2 + 108);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_19c4b30392dd32e174279c73e079de55_Traceguids, v5, v4[10]);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        WPP_19c4b30392dd32e174279c73e079de55_Traceguids,
        *(unsigned int *)(a2 + 232));
    }
  }
  NdisTapiCompleteRequest(*(_QWORD *)(a1 + 520), v4, *(unsigned int *)(a2 + 232));
  ExFreeToNPagedLookasideList(&WanRequestLegacyList, (PVOID)a2);
}

```

## disassembly

```asm
0x140010a1c  push    rbx
0x140010a1e  push    rsi
0x140010a1f  push    rdi
0x140010a20  push    r14
0x140010a22  sub     rsp, 38h
0x140010a26  mov     rbx, rdx
0x140010a29  mov     rsi, rcx
0x140010a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010a33  lea     r14, WPP_GLOBAL_Control
0x140010a3a  cmp     rcx, r14
0x140010a3d  jz      short loc_140010A63
0x140010a3f  test    dword ptr [rcx+2Ch], 100h
0x140010a46  jz      short loc_140010A63
0x140010a48  cmp     byte ptr [rcx+29h], 5
0x140010a4c  jb      short loc_140010A63
0x140010a4e  mov     rcx, [rcx+18h]
0x140010a52  lea     r8, WPP_19c4b30392dd32e174279c73e079de55_Traceguids
0x140010a59  mov     edx, 0Eh
0x140010a5e  call    WPP_SF_
0x140010a63  mov     rdi, [rbx+0E0h]
0x140010a6a  mov     r9d, [rdi+20h]
0x140010a6e  test    r9d, r9d
0x140010a71  jz      short loc_140010A79
0x140010a73  cmp     r9d, 1
0x140010a77  jnz     short loc_140010A7F
0x140010a79  mov     eax, [rbx+6Ch]
0x140010a7c  mov     [rdi+3Ch], eax
0x140010a7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140010a86  cmp     rcx, r14
0x140010a89  jz      short loc_140010AED
0x140010a8b  test    dword ptr [rcx+2Ch], 100h
0x140010a92  jz      short loc_140010AB6
0x140010a94  cmp     byte ptr [rcx+29h], 4
0x140010a98  jb      short loc_140010AB6
0x140010a9a  mov     eax, [rdi+28h]
0x140010a9d  lea     r8, WPP_19c4b30392dd32e174279c73e079de55_Traceguids
0x140010aa4  mov     rcx, [rcx+18h]
0x140010aa8  mov     edx, 0Fh
0x140010aad  mov     [rsp+58h+var_38], eax
0x140010ab1  call    WPP_SF_dd
0x140010ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x140010abd  cmp     rcx, r14
0x140010ac0  jz      short loc_140010AED
0x140010ac2  test    dword ptr [rcx+2Ch], 100h
0x140010ac9  jz      short loc_140010AED
0x140010acb  cmp     byte ptr [rcx+29h], 4
0x140010acf  jb      short loc_140010AED
0x140010ad1  mov     r9d, [rbx+0E8h]
0x140010ad8  lea     r8, WPP_19c4b30392dd32e174279c73e079de55_Traceguids
0x140010adf  mov     rcx, [rcx+18h]
0x140010ae3  mov     edx, 10h
0x140010ae8  call    WPP_SF_d
0x140010aed  mov     r8d, [rbx+0E8h]
0x140010af4  mov     rdx, rdi
0x140010af7  mov     rcx, [rsi+208h]
0x140010afe  call    cs:__imp_NdisTapiCompleteRequest
0x140010b05  nop     dword ptr [rax+rax+00h]
0x140010b0a  mov     rdx, rbx; Entry
0x140010b0d  lea     rcx, WanRequestLegacyList; Lookaside
0x140010b14  call    cs:__imp_ExFreeToNPagedLookasideList
0x140010b1b  nop     dword ptr [rax+rax+00h]
0x140010b20  add     rsp, 38h
0x140010b24  pop     r14
0x140010b26  pop     rdi
0x140010b27  pop     rsi
0x140010b28  pop     rbx
0x140010b29  retn
```
