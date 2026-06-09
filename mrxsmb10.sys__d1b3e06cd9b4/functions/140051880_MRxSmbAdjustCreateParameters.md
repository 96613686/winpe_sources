# MRxSmbAdjustCreateParameters

- ea: `0x140051880`
- end: `0x140051986`
- name: `MRxSmbAdjustCreateParameters`
- size: `262`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140037780`
- `0x1400394f0`
- `0x14004a2f0`

## callees

- `0x14000dfa8`
- `0x140051880`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcessId` at `0x1400518dc`
- `ntoskrnl!IoGetRequestorProcessId` at `0x1400518dc`

## pseudocode

```c
__int64 __fastcall MRxSmbAdjustCreateParameters(__int64 a1, __int64 a2)
{
  IRP *v4; // rcx
  __int64 result; // rax
  char v6; // dl
  __int64 v7; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  if ( *(int *)(a1 + 120) < 0 )
  {
    v7 = *(_QWORD *)(a1 + 72);
    if ( v7 )
      v7 = *(_QWORD *)(v7 + 48);
    *(_QWORD *)(a1 + 544) = 0;
    result = *(_QWORD *)(v7 + 16);
    *(_QWORD *)a2 = *(_QWORD *)(result + 92);
  }
  else
  {
    *(_DWORD *)(a1 + 540) &= 0xFFFFFFCF;
    v4 = *(IRP **)(a1 + 40);
    if ( v4 )
      *(_DWORD *)a2 = IoGetRequestorProcessId(v4);
    *(_BYTE *)(a2 + 4) = 0;
    result = *(_QWORD *)(a1 + 544);
    if ( result && *(_QWORD *)result )
    {
      v6 = 0;
      if ( *(_BYTE *)(*(_QWORD *)result + 8LL) == 1 )
      {
        *(_BYTE *)(a2 + 4) = 1;
        v6 = 1;
      }
      result = *(_QWORD *)(a1 + 544);
      if ( *(_BYTE *)(*(_QWORD *)result + 9LL) )
        *(_BYTE *)(a2 + 4) = v6 | 2;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140051880  mov     [rsp+arg_0], rbx
0x140051885  mov     [rsp+arg_8], rsi
0x14005188a  push    rdi
0x14005188b  sub     rsp, 20h
0x14005188f  mov     rdi, rdx
0x140051892  mov     rbx, rcx
0x140051895  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005189c  lea     rsi, WPP_GLOBAL_Control
0x1400518a3  cmp     rcx, rsi
0x1400518a6  jz      short loc_1400518C6
0x1400518a8  test    dword ptr [rcx+2Ch], 400h
0x1400518af  jz      short loc_1400518C6
0x1400518b1  mov     rcx, [rcx+18h]
0x1400518b5  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x1400518bc  mov     edx, 1Fh
0x1400518c1  call    WPP_SF_
0x1400518c6  cmp     dword ptr [rbx+78h], 0
0x1400518ca  jl      short loc_140051928
0x1400518cc  and     dword ptr [rbx+21Ch], 0FFFFFFCFh
0x1400518d3  mov     rcx, [rbx+28h]; Irp
0x1400518d7  test    rcx, rcx
0x1400518da  jz      short loc_1400518EA
0x1400518dc  call    cs:__imp_IoGetRequestorProcessId
0x1400518e3  nop     dword ptr [rax+rax+00h]
0x1400518e8  mov     [rdi], eax
0x1400518ea  mov     byte ptr [rdi+4], 0
0x1400518ee  mov     rax, [rbx+220h]
0x1400518f5  test    rax, rax
0x1400518f8  jz      short loc_14005194B
0x1400518fa  mov     rcx, [rax]
0x1400518fd  test    rcx, rcx
0x140051900  jz      short loc_14005194B
0x140051902  xor     dl, dl
0x140051904  cmp     byte ptr [rcx+8], 1
0x140051908  jnz     short loc_140051910
0x14005190a  mov     byte ptr [rdi+4], 1
0x14005190e  mov     dl, 1
0x140051910  mov     rax, [rbx+220h]
0x140051917  mov     rcx, [rax]
0x14005191a  cmp     byte ptr [rcx+9], 0
0x14005191e  jz      short loc_14005194B
0x140051920  or      dl, 2
0x140051923  mov     [rdi+4], dl
0x140051926  jmp     short loc_14005194B
0x140051928  mov     rax, [rbx+48h]
0x14005192c  test    rax, rax
0x14005192f  jz      short loc_140051935
0x140051931  mov     rax, [rax+30h]
0x140051935  mov     qword ptr [rbx+220h], 0
0x140051940  mov     rax, [rax+10h]
0x140051944  mov     rcx, [rax+5Ch]
0x140051948  mov     [rdi], rcx
0x14005194b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140051952  cmp     rcx, rsi
0x140051955  jz      short loc_140051975
0x140051957  test    dword ptr [rcx+2Ch], 400h
0x14005195e  jz      short loc_140051975
0x140051960  mov     rcx, [rcx+18h]
0x140051964  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x14005196b  mov     edx, 20h ; ' '
0x140051970  call    WPP_SF_
0x140051975  mov     rbx, [rsp+28h+arg_0]
0x14005197a  mov     rsi, [rsp+28h+arg_8]
0x14005197f  add     rsp, 20h
0x140051983  pop     rdi
0x140051984  retn
```
