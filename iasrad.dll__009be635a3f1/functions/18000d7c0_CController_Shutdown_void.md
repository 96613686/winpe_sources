# CController::Shutdown(void)

- ea: `0x18000d7c0`
- end: `0x18000d947`
- name: `?Shutdown@CController@@UEAAJXZ`
- size: `391`
- prototype: `__int64 __fastcall(CController *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800094e4`
- `0x18000c614`
- `0x18000d7c0`
- `0x18001d31c`
- `0x180030010`

## string_xrefs

- `0x18000d7ef`: `Shutting down Radius Component...`
- `0x18000d84c`: `Radius component can not be shutdown in this state`
- `0x18000d90d`: `Radius component shutdown completed`

## pseudocode

```c
__int64 __fastcall CController::Shutdown(CController *this)
{
  PVOID *v2; // rdx
  __int64 result; // rax
  int v4; // edi

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WppDbgPrint("Shutting down Radius Component...");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  result = *((unsigned int *)this + 322);
  if ( (_DWORD)result )
  {
    if ( (((_DWORD)result - 1) & 0xFFFFFFFD) != 0 )
    {
      if ( v2 != &WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 2u && (*((_DWORD *)v2 + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Radius component can not be shutdown in this state");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
      }
      return 2147549183LL;
    }
    else
    {
      v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 23) + 64LL))(*((_QWORD *)this + 23));
      if ( v4 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("InfoBase shutdown failed");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
      }
      CController::InternalCleanup(this);
      *((_DWORD *)this + 322) = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Radius component shutdown completed");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids, "NPSRAD");
      }
      return (unsigned int)v4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d7c0  push    rbx
0x18000d7c2  push    rbp
0x18000d7c3  push    rsi
0x18000d7c4  push    rdi
0x18000d7c5  sub     rsp, 28h
0x18000d7c9  mov     rbx, rcx
0x18000d7cc  mov     rdx, cs:WPP_GLOBAL_Control
0x18000d7d3  lea     rbp, WPP_GLOBAL_Control
0x18000d7da  mov     esi, 100h
0x18000d7df  cmp     rdx, rbp
0x18000d7e2  jz      short loc_18000D825
0x18000d7e4  cmp     byte ptr [rdx+19h], 4
0x18000d7e8  jb      short loc_18000D825
0x18000d7ea  test    [rdx+1Ch], esi
0x18000d7ed  jz      short loc_18000D825
0x18000d7ef  lea     rcx, aShuttingDownRa; "Shutting down Radius Component..."
0x18000d7f6  call    WppDbgPrint
0x18000d7fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d802  lea     r9, aNpsrad; "NPSRAD"
0x18000d809  mov     edx, 35h ; '5'
0x18000d80e  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000d815  mov     rcx, [rcx+10h]
0x18000d819  call    WPP_SF_s
0x18000d81e  mov     rdx, cs:WPP_GLOBAL_Control
0x18000d825  mov     eax, [rbx+508h]
0x18000d82b  test    eax, eax
0x18000d82d  jz      loc_18000D93E
0x18000d833  dec     eax
0x18000d835  test    eax, 0FFFFFFFDh
0x18000d83a  jz      short loc_18000D885
0x18000d83c  cmp     rdx, rbp
0x18000d83f  jz      short loc_18000D87B
0x18000d841  cmp     byte ptr [rdx+19h], 2
0x18000d845  jb      short loc_18000D87B
0x18000d847  test    [rdx+1Ch], esi
0x18000d84a  jz      short loc_18000D87B
0x18000d84c  lea     rcx, aRadiusComponen; "Radius component can not be shutdown in"...
0x18000d853  call    WppDbgPrint
0x18000d858  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d85f  lea     r9, aNpsrad; "NPSRAD"
0x18000d866  mov     edx, 36h ; '6'
0x18000d86b  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000d872  mov     rcx, [rcx+10h]
0x18000d876  call    WPP_SF_s
0x18000d87b  mov     eax, 8000FFFFh
0x18000d880  jmp     loc_18000D93E
0x18000d885  mov     rcx, [rbx+0B8h]
0x18000d88c  mov     rax, [rcx]
0x18000d88f  mov     rax, [rax+40h]
0x18000d893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d898  mov     edi, eax
0x18000d89a  test    eax, eax
0x18000d89c  jns     short loc_18000D8E4
0x18000d89e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8a5  cmp     rcx, rbp
0x18000d8a8  jz      short loc_18000D8E4
0x18000d8aa  cmp     byte ptr [rcx+19h], 2
0x18000d8ae  jb      short loc_18000D8E4
0x18000d8b0  test    [rcx+1Ch], esi
0x18000d8b3  jz      short loc_18000D8E4
0x18000d8b5  lea     rcx, aInfobaseShutdo; "InfoBase shutdown failed"
0x18000d8bc  call    WppDbgPrint
0x18000d8c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8c8  lea     r9, aNpsrad; "NPSRAD"
0x18000d8cf  mov     edx, 37h ; '7'
0x18000d8d4  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000d8db  mov     rcx, [rcx+10h]
0x18000d8df  call    WPP_SF_s
0x18000d8e4  mov     rcx, rbx; this
0x18000d8e7  call    ?InternalCleanup@CController@@AEAAXXZ; CController::InternalCleanup(void)
0x18000d8ec  mov     dword ptr [rbx+508h], 0
0x18000d8f6  mov     rax, cs:WPP_GLOBAL_Control
0x18000d8fd  cmp     rax, rbp
0x18000d900  jz      short loc_18000D93C
0x18000d902  cmp     byte ptr [rax+19h], 4
0x18000d906  jb      short loc_18000D93C
0x18000d908  test    [rax+1Ch], esi
0x18000d90b  jz      short loc_18000D93C
0x18000d90d  lea     rcx, aRadiusComponen_3; "Radius component shutdown completed"
0x18000d914  call    WppDbgPrint
0x18000d919  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d920  lea     r9, aNpsrad; "NPSRAD"
0x18000d927  mov     edx, 38h ; '8'
0x18000d92c  lea     r8, WPP_783bdad7903c3a60e377174e2ef9c4c6_Traceguids
0x18000d933  mov     rcx, [rcx+10h]
0x18000d937  call    WPP_SF_s
0x18000d93c  mov     eax, edi
0x18000d93e  add     rsp, 28h
0x18000d942  pop     rdi
0x18000d943  pop     rsi
0x18000d944  pop     rbp
0x18000d945  pop     rbx
0x18000d946  retn
```
