# EapHost::Peer::ConnectionSessionInfo::GetHostApis(void)

- ea: `0x18000c204`
- end: `0x18000c279`
- name: `?GetHostApis@ConnectionSessionInfo@Peer@EapHost@@QEAA?AV?$CComPtr@UIEapHostPeerSessionApis@@@ATL@@XZ`
- size: `117`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180006100`
- `0x180007d40`
- `0x1800080c0`
- `0x18000bef4`
- `0x18000c88c`
- `0x18000cae8`

## callees

- `0x18000ade4`
- `0x18000c204`
- `0x18000f010`

## pseudocode

```c
_QWORD *__fastcall EapHost::Peer::ConnectionSessionInfo::GetHostApis(__int64 a1, _QWORD *a2)
{
  int v3; // eax

  *a2 = 0;
  v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, _QWORD *))(**(_QWORD **)(a1 + 184) + 40LL))(
         *(_QWORD *)(a1 + 184),
         *(unsigned int *)(a1 + 196),
         &GUID_09dbbc77_588f_4517_a485_74a29759f54c,
         a2);
  if ( v3 < 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids, (unsigned int)v3);
  return a2;
}

```

## disassembly

```asm
0x18000c204  push    rbx
0x18000c206  sub     rsp, 30h
0x18000c20a  mov     rbx, rdx
0x18000c20d  mov     rdx, rcx
0x18000c210  mov     qword ptr [rbx], 0
0x18000c217  mov     rcx, [rcx+0B8h]
0x18000c21e  mov     rax, [rcx]
0x18000c221  mov     r9, rbx
0x18000c224  lea     r8, _GUID_09dbbc77_588f_4517_a485_74a29759f54c
0x18000c22b  mov     edx, [rdx+0C4h]
0x18000c231  mov     rax, [rax+28h]
0x18000c235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c23a  test    eax, eax
0x18000c23c  jns     short loc_18000C26F
0x18000c23e  lea     rdx, WPP_GLOBAL_Control
0x18000c245  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c24c  cmp     rcx, rdx
0x18000c24f  jz      short loc_18000C26F
0x18000c251  test    byte ptr [rcx+1Ch], 1
0x18000c255  jz      short loc_18000C26F
0x18000c257  mov     edx, 0Eh
0x18000c25c  mov     r9d, eax
0x18000c25f  lea     r8, WPP_a2bbe9c3264d3ee44dc19a0825749d97_Traceguids
0x18000c266  mov     rcx, [rcx+10h]
0x18000c26a  call    WPP_SF_d
0x18000c26f  mov     rax, rbx
0x18000c272  add     rsp, 30h
0x18000c276  pop     rbx
0x18000c277  retn
```
