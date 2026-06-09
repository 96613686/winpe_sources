# SpFreeCredentialsHandle(unsigned __int64)

- ea: `0x18000ce00`
- end: `0x18000cf72`
- name: `?SpFreeCredentialsHandle@@YAJ_K@Z`
- size: `370`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000afc0`
- `0x18000ce00`
- `0x180023e30`
- `0x18002e800`

## import_xrefs

- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000ce50`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18000ce50`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000ce3e`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000ce3e`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000cedf`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000cedf`
- `ntdll!RtlReleaseResource` at `0x18000ce6f`
- `ntdll!RtlReleaseResource` at `0x18000ce6f`

## pseudocode

```c
__int64 __fastcall SpFreeCredentialsHandle(struct _PKU2U_SECONDARY_CREDENTIAL *a1)
{
  unsigned int v2; // ebx
  volatile signed __int32 *v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  PVOID *v6; // rcx
  struct _PKU2U_SECONDARY_CREDENTIAL *Buffer[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_2429819d036b3e2177922931f9f6578d_Traceguids, a1);
  v2 = 0;
  Buffer[0] = a1;
  Buffer[1] = 0;
  RtlAcquireResourceExclusive(&Pku2uGlobalCredTableLock, 1u);
  v3 = (volatile signed __int32 *)RtlLookupElementGenericTableAvl(&Pku2uGlobalCredTable, Buffer);
  if ( v3 )
  {
    _InterlockedDecrement(v3 + 2);
    if ( *((int *)v3 + 2) <= 0 && RtlDeleteElementGenericTableAvl(&Pku2uGlobalCredTable, Buffer) )
    {
      *((_DWORD *)Buffer[0] + 3) = 0;
      Pku2uDereferenceSecondaryCredential(Buffer[0]);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_2429819d036b3e2177922931f9f6578d_Traceguids, a1);
    v2 = -1073741816;
  }
  RtlReleaseResource(&Pku2uGlobalCredTableLock);
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_2429819d036b3e2177922931f9f6578d_Traceguids, a1);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
      WPP_SF_Dq(v6[2], v4, v5, v2, a1);
  }
  return v2;
}

```

## disassembly

```asm
0x18000ce00  mov     [rsp+arg_0], rbx
0x18000ce05  mov     [rsp+arg_8], rsi
0x18000ce0a  push    rdi
0x18000ce0b  sub     rsp, 40h
0x18000ce0f  mov     rdi, rcx
0x18000ce12  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce19  lea     rsi, WPP_GLOBAL_Control
0x18000ce20  cmp     rcx, rsi
0x18000ce23  jnz     loc_18000CEAC
0x18000ce29  xor     ebx, ebx
0x18000ce2b  mov     [rsp+48h+Buffer], rdi
0x18000ce30  mov     dl, 1; Wait
0x18000ce32  mov     [rsp+48h+var_10], rbx
0x18000ce37  lea     rcx, ?Pku2uGlobalCredTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18000ce3e  call    cs:__imp_RtlAcquireResourceExclusive
0x18000ce44  lea     rdx, [rsp+48h+Buffer]; Buffer
0x18000ce49  lea     rcx, ?Pku2uGlobalCredTable@@3U_RTL_AVL_TABLE@@A; Table
0x18000ce50  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18000ce56  test    rax, rax
0x18000ce59  jz      loc_18000CF04
0x18000ce5f  lock dec dword ptr [rax+8]
0x18000ce63  cmp     [rax+8], ebx
0x18000ce66  jle     short loc_18000CED3
0x18000ce68  lea     rcx, ?Pku2uGlobalCredTableLock@@3U_RTL_RESOURCE@@A; Resource
0x18000ce6f  call    cs:__imp_RtlReleaseResource
0x18000ce75  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ce7c  cmp     rcx, rsi
0x18000ce7f  jz      short loc_18000CE9A
0x18000ce81  test    byte ptr [rcx+1Ch], 10h
0x18000ce85  jnz     loc_18000CF38
0x18000ce8b  cmp     rcx, rsi
0x18000ce8e  jz      short loc_18000CE9A
0x18000ce90  test    byte ptr [rcx+1Ch], 8
0x18000ce94  jnz     loc_18000CF5C
0x18000ce9a  mov     rsi, [rsp+48h+arg_8]
0x18000ce9f  mov     eax, ebx
0x18000cea1  mov     rbx, [rsp+48h+arg_0]
0x18000cea6  add     rsp, 40h
0x18000ceaa  pop     rdi
0x18000ceab  retn
0x18000ceac  test    byte ptr [rcx+1Ch], 8
0x18000ceb0  jz      loc_18000CE29
0x18000ceb6  mov     rcx, [rcx+10h]
0x18000ceba  lea     r8, WPP_2429819d036b3e2177922931f9f6578d_Traceguids
0x18000cec1  mov     edx, 45h ; 'E'
0x18000cec6  mov     r9, rdi
0x18000cec9  call    WPP_SF_q
0x18000cece  jmp     loc_18000CE29
0x18000ced3  lea     rdx, [rsp+48h+Buffer]; Buffer
0x18000ced8  lea     rcx, ?Pku2uGlobalCredTable@@3U_RTL_AVL_TABLE@@A; Table
0x18000cedf  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18000cee5  test    al, al
0x18000cee7  jz      loc_18000CE68
0x18000ceed  mov     rax, [rsp+48h+Buffer]
0x18000cef2  mov     [rax+0Ch], ebx
0x18000cef5  mov     rcx, [rsp+48h+Buffer]; struct _PKU2U_SECONDARY_CREDENTIAL *
0x18000cefa  call    ?Pku2uDereferenceSecondaryCredential@@YAXPEAU_PKU2U_SECONDARY_CREDENTIAL@@@Z; Pku2uDereferenceSecondaryCredential(_PKU2U_SECONDARY_CREDENTIAL *)
0x18000ceff  jmp     loc_18000CE68
0x18000cf04  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf0b  cmp     rcx, rsi
0x18000cf0e  jz      short loc_18000CF2E
0x18000cf10  test    byte ptr [rcx+1Ch], 10h
0x18000cf14  jz      short loc_18000CF2E
0x18000cf16  mov     rcx, [rcx+10h]
0x18000cf1a  lea     r8, WPP_2429819d036b3e2177922931f9f6578d_Traceguids
0x18000cf21  mov     edx, 0Dh
0x18000cf26  mov     r9, rdi
0x18000cf29  call    WPP_SF_q
0x18000cf2e  mov     ebx, 0C0000008h
0x18000cf33  jmp     loc_18000CE68
0x18000cf38  mov     rcx, [rcx+10h]
0x18000cf3c  lea     r8, WPP_2429819d036b3e2177922931f9f6578d_Traceguids
0x18000cf43  mov     edx, 46h ; 'F'
0x18000cf48  mov     r9, rdi
0x18000cf4b  call    WPP_SF_q
0x18000cf50  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf57  jmp     loc_18000CE8B
0x18000cf5c  mov     rcx, [rcx+10h]
0x18000cf60  mov     r9d, ebx
0x18000cf63  mov     [rsp+48h+var_28], rdi
0x18000cf68  call    WPP_SF_Dq
0x18000cf6d  jmp     loc_18000CE9A
```
