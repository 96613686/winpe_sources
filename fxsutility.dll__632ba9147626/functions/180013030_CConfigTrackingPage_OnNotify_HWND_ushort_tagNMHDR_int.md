# CConfigTrackingPage::OnNotify(HWND__ *,ushort,tagNMHDR *,int &)

- ea: `0x180013030`
- end: `0x1800130cd`
- name: `?OnNotify@CConfigTrackingPage@@UEAAKPEAUHWND__@@GPEAUtagNMHDR@@AEAH@Z`
- size: `157`
- prototype: `unsigned int __fastcall(CConfigTrackingPage *__hidden this, HWND, unsigned __int16, struct tagNMHDR *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180005eac`
- `0x180013030`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CConfigTrackingPage::OnNotify(
        CConfigTrackingPage *this,
        HWND a2,
        __int16 a3,
        struct tagNMHDR *a4,
        int *a5)
{
  unsigned int v8; // r8d

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids);
  }
  v8 = 0;
  if ( a3 == 4204 && ((a4->code + 4) & 0xFFFFFFFD) == 0 )
  {
    v8 = (*(__int64 (__fastcall **)(CConfigTrackingPage *, HWND, _QWORD))(*(_QWORD *)this + 32LL))(this, a2, 0);
    *a5 = v8 == 0;
  }
  return v8;
}

```

## disassembly

```asm
0x180013030  mov     [rsp+arg_0], rbx
0x180013035  mov     [rsp+arg_8], rsi
0x18001303a  push    rdi
0x18001303b  sub     rsp, 20h
0x18001303f  mov     rdi, r9
0x180013042  movzx   ebx, r8w
0x180013046  mov     rsi, rcx
0x180013049  mov     rcx, cs:WPP_GLOBAL_Control
0x180013050  lea     rax, WPP_GLOBAL_Control
0x180013057  cmp     rcx, rax
0x18001305a  jz      short loc_180013080
0x18001305c  test    dword ptr [rcx+1Ch], 100h
0x180013063  jz      short loc_180013080
0x180013065  cmp     byte ptr [rcx+19h], 5
0x180013069  jb      short loc_180013080
0x18001306b  mov     rcx, [rcx+10h]
0x18001306f  lea     r8, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids
0x180013076  mov     edx, 11h
0x18001307b  call    WPP_SF_
0x180013080  xor     r8d, r8d
0x180013083  mov     eax, 106Ch
0x180013088  cmp     ax, bx
0x18001308b  jnz     short loc_1800130BA
0x18001308d  mov     eax, [rdi+10h]
0x180013090  add     eax, 4
0x180013093  test    eax, 0FFFFFFFDh
0x180013098  jnz     short loc_1800130BA
0x18001309a  mov     rax, [rsi]
0x18001309d  mov     rcx, rsi
0x1800130a0  mov     rax, [rax+20h]
0x1800130a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130a9  mov     rcx, [rsp+28h+arg_20]
0x1800130ae  xor     edx, edx
0x1800130b0  test    eax, eax
0x1800130b2  mov     r8d, eax
0x1800130b5  setz    dl
0x1800130b8  mov     [rcx], edx
0x1800130ba  mov     rbx, [rsp+28h+arg_0]
0x1800130bf  mov     eax, r8d
0x1800130c2  mov     rsi, [rsp+28h+arg_8]
0x1800130c7  add     rsp, 20h
0x1800130cb  pop     rdi
0x1800130cc  retn
```
