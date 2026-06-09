# CController::Resume(void)

- ea: `0x18000d5e0`
- end: `0x18000d790`
- name: `?Resume@CController@@UEAAJXZ`
- size: `432`
- prototype: `__int64 __fastcall(CController *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800094e4`
- `0x18000c838`
- `0x18000d5e0`
- `0x18001a27c`
- `0x18001a4e8`
- `0x18001d31c`
- `0x180030010`

## string_xrefs

- `0x18000d611`: `Resuming Radius component...`
- `0x18000d660`: `Can not resume Radius component in current state`
- `0x18000d73e`: `Radius componend resumed.`

## pseudocode

```c
__int64 __fastcall CController::Resume(CController *this)
{
  PVOID *v2; // rax
  int v4; // edi
  __int64 v5; // rdx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Resuming Radius component...");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 322) == 3 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 23) + 104LL))(*((_QWORD *)this + 23));
    if ( v4 >= 0 )
    {
      v4 = CPorts::OpenSockets((CController *)((char *)this + 192));
      if ( v4 < 0
        || (v4 = CPorts::OpenSockets((CController *)((char *)this + 728)), v4 < 0)
        || (v4 = CController::InternalInit(this), v4 < 0) )
      {
        CPorts::CloseSockets((CController *)((char *)this + 192));
        CPorts::CloseSockets((CController *)((char *)this + 728));
        return (unsigned int)v4;
      }
      *((_DWORD *)this + 322) = 2;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      {
        return (unsigned int)v4;
      }
      WppDbgPrint("Radius componend resumed.");
      v5 = 66;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      {
        return (unsigned int)v4;
      }
      WppDbgPrint("Unable to resume Infobase");
      v5 = 65;
    }
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    return (unsigned int)v4;
  }
  if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 2u && (*((_DWORD *)v2 + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Can not resume Radius component in current state");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
  }
  return 2147549183LL;
}

```

## disassembly

```asm
0x18000d5e0  push    rbx
0x18000d5e2  push    rbp
0x18000d5e3  push    rsi
0x18000d5e4  push    rdi
0x18000d5e5  push    r14
0x18000d5e7  sub     rsp, 20h
0x18000d5eb  mov     rbx, rcx
0x18000d5ee  mov     rax, cs:WPP_GLOBAL_Control
0x18000d5f5  lea     r14, WPP_GLOBAL_Control
0x18000d5fc  mov     ebp, 100h
0x18000d601  cmp     rax, r14
0x18000d604  jz      short loc_18000D647
0x18000d606  cmp     byte ptr [rax+19h], 4
0x18000d60a  jb      short loc_18000D647
0x18000d60c  test    [rax+1Ch], ebp
0x18000d60f  jz      short loc_18000D647
0x18000d611  lea     rcx, aResumingRadius; "Resuming Radius component..."
0x18000d618  call    WppDbgPrint
0x18000d61d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d624  lea     r9, aNpsrad; "NPSRAD"
0x18000d62b  mov     edx, 3Fh ; '?'
0x18000d630  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000d637  mov     rcx, [rcx+10h]
0x18000d63b  call    WPP_SF_s
0x18000d640  mov     rax, cs:WPP_GLOBAL_Control
0x18000d647  cmp     dword ptr [rbx+508h], 3
0x18000d64e  jz      short loc_18000D699
0x18000d650  cmp     rax, r14
0x18000d653  jz      short loc_18000D68F
0x18000d655  cmp     byte ptr [rax+19h], 2
0x18000d659  jb      short loc_18000D68F
0x18000d65b  test    [rax+1Ch], ebp
0x18000d65e  jz      short loc_18000D68F
0x18000d660  lea     rcx, aCanNotResumeRa; "Can not resume Radius component in curr"...
0x18000d667  call    WppDbgPrint
0x18000d66c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d673  lea     r9, aNpsrad; "NPSRAD"
0x18000d67a  mov     edx, 40h ; '@'
0x18000d67f  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000d686  mov     rcx, [rcx+10h]
0x18000d68a  call    WPP_SF_s
0x18000d68f  mov     eax, 8000FFFFh
0x18000d694  jmp     loc_18000D785
0x18000d699  mov     rcx, [rbx+0B8h]
0x18000d6a0  mov     rax, [rcx]
0x18000d6a3  mov     rax, [rax+68h]
0x18000d6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6ac  mov     edi, eax
0x18000d6ae  test    eax, eax
0x18000d6b0  jns     short loc_18000D6E8
0x18000d6b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6b9  cmp     rcx, r14
0x18000d6bc  jz      loc_18000D783
0x18000d6c2  cmp     byte ptr [rcx+19h], 2
0x18000d6c6  jb      loc_18000D783
0x18000d6cc  test    [rcx+1Ch], ebp
0x18000d6cf  jz      loc_18000D783
0x18000d6d5  lea     rcx, aUnableToResume; "Unable to resume Infobase"
0x18000d6dc  call    WppDbgPrint
0x18000d6e1  mov     edx, 41h ; 'A'
0x18000d6e6  jmp     short loc_18000D74F
0x18000d6e8  lea     rsi, [rbx+0C0h]
0x18000d6ef  mov     rcx, rsi; this
0x18000d6f2  call    ?OpenSockets@CPorts@@QEAAJXZ; CPorts::OpenSockets(void)
0x18000d6f7  mov     edi, eax
0x18000d6f9  test    eax, eax
0x18000d6fb  js      short loc_18000D76F
0x18000d6fd  lea     rcx, [rbx+2D8h]; this
0x18000d704  call    ?OpenSockets@CPorts@@QEAAJXZ; CPorts::OpenSockets(void)
0x18000d709  mov     edi, eax
0x18000d70b  test    eax, eax
0x18000d70d  js      short loc_18000D76F
0x18000d70f  mov     rcx, rbx; this
0x18000d712  call    ?InternalInit@CController@@AEAAJXZ; CController::InternalInit(void)
0x18000d717  mov     edi, eax
0x18000d719  test    eax, eax
0x18000d71b  js      short loc_18000D76F
0x18000d71d  mov     dword ptr [rbx+508h], 2
0x18000d727  mov     rax, cs:WPP_GLOBAL_Control
0x18000d72e  cmp     rax, r14
0x18000d731  jz      short loc_18000D783
0x18000d733  cmp     byte ptr [rax+19h], 4
0x18000d737  jb      short loc_18000D783
0x18000d739  test    [rax+1Ch], ebp
0x18000d73c  jz      short loc_18000D783
0x18000d73e  lea     rcx, aRadiusComponen_0; "Radius componend resumed."
0x18000d745  call    WppDbgPrint
0x18000d74a  mov     edx, 42h ; 'B'
0x18000d74f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d756  lea     r9, aNpsrad; "NPSRAD"
0x18000d75d  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000d764  mov     rcx, [rcx+10h]
0x18000d768  call    WPP_SF_s
0x18000d76d  jmp     short loc_18000D783
0x18000d76f  mov     rcx, rsi; this
0x18000d772  call    ?CloseSockets@CPorts@@QEAAXXZ; CPorts::CloseSockets(void)
0x18000d777  lea     rcx, [rbx+2D8h]; this
0x18000d77e  call    ?CloseSockets@CPorts@@QEAAXXZ; CPorts::CloseSockets(void)
0x18000d783  mov     eax, edi
0x18000d785  add     rsp, 20h
0x18000d789  pop     r14
0x18000d78b  pop     rdi
0x18000d78c  pop     rsi
0x18000d78d  pop     rbp
0x18000d78e  pop     rbx
0x18000d78f  retn
```
