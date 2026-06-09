# CImpersonate::~CImpersonate(void)

- ea: `0x180028250`
- end: `0x180028334`
- name: `??1CImpersonate@@UEAA@XZ`
- size: `228`
- prototype: `void __fastcall(CImpersonate *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180028340`
- `0x180028b30`
- `0x18003072e`

## callees

- `0x1800049ac`
- `0x180028250`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1800282b9`
- `RPCRT4!RpcRevertToSelf` at `0x1800282b9`
- `ADVAPI32!RevertToSelf` at `0x18002827e`
- `ADVAPI32!RevertToSelf` at `0x1800282e6`
- `ADVAPI32!RevertToSelf` at `0x18002827e`
- `ADVAPI32!RevertToSelf` at `0x1800282e6`
- `KERNEL32!CloseHandle` at `0x18002826c`
- `KERNEL32!CloseHandle` at `0x18002826c`
- `KERNEL32!GetLastError` at `0x18002828c`
- `KERNEL32!GetLastError` at `0x1800282f0`
- `KERNEL32!GetLastError` at `0x18002828c`
- `KERNEL32!GetLastError` at `0x1800282f0`

## pseudocode

```c
void __fastcall CImpersonate::~CImpersonate(CImpersonate *this)
{
  void *v2; // rcx
  DWORD LastError; // eax
  _QWORD *v4; // rcx
  __int64 v5; // rdx

  *(_QWORD *)this = &CImpersonate::`vftable';
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
    CloseHandle(v2);
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_BYTE *)this + 28) )
    {
      if ( !RevertToSelf() )
      {
        LastError = GetLastError();
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        {
          v5 = 14;
LABEL_17:
          WPP_SF_d(v4[32], v5, &WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids, LastError);
        }
      }
    }
    else
    {
      LastError = RpcRevertToSelf();
      if ( LastError )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        {
          v5 = 15;
          goto LABEL_17;
        }
      }
    }
  }
  else if ( !RevertToSelf() )
  {
    LastError = GetLastError();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v5 = 16;
      goto LABEL_17;
    }
  }
}

```

## disassembly

```asm
0x180028250  push    rbx
0x180028252  sub     rsp, 20h
0x180028256  mov     rbx, rcx
0x180028259  lea     rax, ??_7CImpersonate@@6B@; const CImpersonate::`vftable'
0x180028260  mov     [rcx], rax
0x180028263  mov     rcx, [rcx+10h]; hObject
0x180028267  test    rcx, rcx
0x18002826a  jz      short loc_180028272
0x18002826c  call    cs:__imp_CloseHandle
0x180028272  cmp     dword ptr [rbx+8], 0
0x180028276  jz      short loc_1800282E6
0x180028278  cmp     byte ptr [rbx+1Ch], 0
0x18002827c  jz      short loc_1800282B9
0x18002827e  call    cs:__imp_RevertToSelf
0x180028284  test    eax, eax
0x180028286  jnz     loc_18002832E
0x18002828c  call    cs:__imp_GetLastError
0x180028292  lea     rdx, WPP_GLOBAL_Control
0x180028299  mov     rcx, cs:WPP_GLOBAL_Control
0x1800282a0  cmp     rcx, rdx
0x1800282a3  jz      loc_18002832E
0x1800282a9  test    byte ptr [rcx+10Ch], 1
0x1800282b0  jz      short loc_18002832E
0x1800282b2  mov     edx, 0Eh
0x1800282b7  jmp     short loc_180028317
0x1800282b9  call    cs:__imp_RpcRevertToSelf
0x1800282bf  test    eax, eax
0x1800282c1  jz      short loc_18002832E
0x1800282c3  lea     rdx, WPP_GLOBAL_Control
0x1800282ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800282d1  cmp     rcx, rdx
0x1800282d4  jz      short loc_18002832E
0x1800282d6  test    byte ptr [rcx+10Ch], 1
0x1800282dd  jz      short loc_18002832E
0x1800282df  mov     edx, 0Fh
0x1800282e4  jmp     short loc_180028317
0x1800282e6  call    cs:__imp_RevertToSelf
0x1800282ec  test    eax, eax
0x1800282ee  jnz     short loc_18002832E
0x1800282f0  call    cs:__imp_GetLastError
0x1800282f6  lea     rdx, WPP_GLOBAL_Control
0x1800282fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180028304  cmp     rcx, rdx
0x180028307  jz      short loc_18002832E
0x180028309  test    byte ptr [rcx+10Ch], 1
0x180028310  jz      short loc_18002832E
0x180028312  mov     edx, 10h
0x180028317  mov     r9d, eax
0x18002831a  lea     r8, WPP_3ad5d6db3aa03cd5633c619672a0f723_Traceguids
0x180028321  mov     rcx, [rcx+100h]
0x180028328  call    WPP_SF_d
0x18002832d  nop
0x18002832e  add     rsp, 20h
0x180028332  pop     rbx
0x180028333  retn
```
