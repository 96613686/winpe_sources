# OneXFreeRuntimeState

- ea: `0x180032094`
- end: `0x180032164`
- name: `OneXFreeRuntimeState`
- size: `208`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180016fc8`
- `0x18001a060`
- `0x180031dc4`
- `0x180031ed8`

## callees

- `0x180032094`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800320c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800320c0`
- `MobileNetworking!FreeMemory` at `0x1800320ed`
- `MobileNetworking!FreeMemory` at `0x180032129`
- `MobileNetworking!FreeMemory` at `0x180032153`
- `MobileNetworking!FreeMemory` at `0x1800320ed`
- `MobileNetworking!FreeMemory` at `0x180032129`
- `MobileNetworking!FreeMemory` at `0x180032153`

## string_xrefs

- `0x18003211f`: `OneXDeleteEAPCredentials`

## pseudocode

```c
void __fastcall OneXFreeRuntimeState(__int64 a1)
{
  __int64 v2; // rax
  void *v3; // rcx
  _BYTE *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    v6 = a1;
    v2 = a1;
    if ( (*(_BYTE *)a1 & 1) != 0 )
    {
      v3 = *(void **)(a1 + 8);
      if ( v3 )
      {
        CloseHandle(v3);
        v2 = v6;
      }
    }
    if ( (*(_BYTE *)v2 & 2) != 0 && *(_DWORD *)(v2 + 16) && *(_QWORD *)(v2 + 24) )
      FreeMemory(v2 + 24, "OneXFreeRuntimeState", 307);
    if ( (*(_BYTE *)a1 & 4) != 0 )
    {
      if ( *(_DWORD *)(a1 + 44) )
      {
        v4 = *(_BYTE **)(a1 + 48);
        if ( v4 )
        {
          v5 = *(unsigned int *)(a1 + 44);
          do
          {
            *v4++ = 0;
            --v5;
          }
          while ( v5 );
          FreeMemory(a1 + 48, "OneXDeleteEAPCredentials", 286);
          *(_DWORD *)a1 &= ~4u;
          *(_QWORD *)(a1 + 40) = 0;
          *(_QWORD *)(a1 + 48) = 0;
        }
      }
    }
    FreeMemory(&v6, "OneXFreeRuntimeState", 312);
  }
}

```

## disassembly

```asm
0x180032094  test    rcx, rcx
0x180032097  jz      locret_180032163
0x18003209d  mov     [rsp+arg_8], rbx
0x1800320a2  push    rdi
0x1800320a3  sub     rsp, 20h
0x1800320a7  mov     [rsp+28h+arg_0], rcx
0x1800320ac  mov     rbx, rcx
0x1800320af  test    byte ptr [rcx], 1
0x1800320b2  mov     rax, rcx
0x1800320b5  jz      short loc_1800320CB
0x1800320b7  mov     rcx, [rcx+8]; hObject
0x1800320bb  test    rcx, rcx
0x1800320be  jz      short loc_1800320CB
0x1800320c0  call    cs:__imp_CloseHandle
0x1800320c6  mov     rax, [rsp+28h+arg_0]
0x1800320cb  test    byte ptr [rax], 2
0x1800320ce  jz      short loc_1800320F3
0x1800320d0  cmp     dword ptr [rax+10h], 0
0x1800320d4  jz      short loc_1800320F3
0x1800320d6  lea     rcx, [rax+18h]
0x1800320da  cmp     qword ptr [rcx], 0
0x1800320de  jz      short loc_1800320F3
0x1800320e0  mov     r8d, 133h
0x1800320e6  lea     rdx, aOnexfreeruntim; "OneXFreeRuntimeState"
0x1800320ed  call    cs:__imp_FreeMemory
0x1800320f3  test    byte ptr [rbx], 4
0x1800320f6  jz      short loc_180032141
0x1800320f8  cmp     dword ptr [rbx+2Ch], 0
0x1800320fc  jz      short loc_180032141
0x1800320fe  lea     rdi, [rbx+30h]
0x180032102  mov     rax, [rdi]
0x180032105  test    rax, rax
0x180032108  jz      short loc_180032141
0x18003210a  mov     ecx, [rbx+2Ch]
0x18003210d  mov     byte ptr [rax], 0
0x180032110  inc     rax
0x180032113  sub     rcx, 1
0x180032117  jnz     short loc_18003210D
0x180032119  mov     r8d, 11Eh
0x18003211f  lea     rdx, aOnexdeleteeapc; "OneXDeleteEAPCredentials"
0x180032126  mov     rcx, rdi
0x180032129  call    cs:__imp_FreeMemory
0x18003212f  and     dword ptr [rbx], 0FFFFFFFBh
0x180032132  mov     qword ptr [rbx+28h], 0
0x18003213a  mov     qword ptr [rdi], 0
0x180032141  mov     r8d, 138h
0x180032147  lea     rdx, aOnexfreeruntim; "OneXFreeRuntimeState"
0x18003214e  lea     rcx, [rsp+28h+arg_0]
0x180032153  call    cs:__imp_FreeMemory
0x180032159  mov     rbx, [rsp+28h+arg_8]
0x18003215e  add     rsp, 20h
0x180032162  pop     rdi
0x180032163  retn
```
