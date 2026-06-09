# CWriteEngineSectionResources::WaitForNextReadBuffer(ulong *)

- ea: `0x18000b7c8`
- end: `0x18000b989`
- name: `?WaitForNextReadBuffer@CWriteEngineSectionResources@@QEAAJPEAK@Z`
- size: `449`
- prototype: `__int64 __fastcall(HANDLE *this, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b510`

## callees

- `0x18000b7c8`
- `0x180014134`
- `0x180016778`
- `0x180049880`

## import_xrefs

- `USER32!MsgWaitForMultipleObjects` at `0x18000b874`
- `USER32!MsgWaitForMultipleObjects` at `0x18000b874`

## pseudocode

```c
__int64 __fastcall CWriteEngineSectionResources::WaitForNextReadBuffer(HANDLE *this, unsigned int *a2)
{
  unsigned int v2; // ebx
  HANDLE v5; // rax
  __int64 v6; // rcx
  DWORD v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  HANDLE pHandles[3]; // [rsp+30h] [rbp-28h] BYREF

  v2 = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 23, &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids);
    }
    return (unsigned int)-2147467261;
  }
  *a2 = -2097152;
  pHandles[0] = this[3];
  v5 = this[7];
  v6 = *((unsigned int *)this + 16);
  pHandles[1] = v5;
  pHandles[2] = *((HANDLE *)this[5] + v6);
  v7 = MsgWaitForMultipleObjects(3u, pHandles, 0, 0xFFFFFFFF, 0);
  switch ( v7 )
  {
    case 0u:
      v2 = -1062600702;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 225) < 2u )
      {
        return v2;
      }
      v9 = v7 + 24;
      goto LABEL_12;
    case 1u:
      v2 = -1062600702;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 225) < 2u )
      {
        return v2;
      }
      v9 = 25;
LABEL_12:
      WPP_SF_(v8[27], v9, &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids);
      return v2;
    case 2u:
      *a2 = *((_DWORD *)this + 16);
      *((_DWORD *)this + 16) = (unsigned int)(*((_DWORD *)this + 16) + 1) % *((_DWORD *)this + 8);
      break;
    default:
      v2 = -2147467259;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 2u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 27), 26, &WPP_d9598978672c34cd509ac261b9388a6f_Traceguids, v7, v7);
      }
      break;
  }
  return v2;
}

```

## disassembly

```asm
0x18000b7c8  mov     [rsp+arg_10], rbx
0x18000b7cd  mov     [rsp+arg_18], rsi
0x18000b7d2  push    rdi
0x18000b7d3  sub     rsp, 50h
0x18000b7d7  mov     rax, cs:__security_cookie
0x18000b7de  xor     rax, rsp
0x18000b7e1  mov     [rsp+58h+var_10], rax
0x18000b7e6  xor     ebx, ebx
0x18000b7e8  mov     rsi, rdx
0x18000b7eb  mov     rdi, rcx
0x18000b7ee  test    rdx, rdx
0x18000b7f1  jnz     short loc_18000B838
0x18000b7f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7fa  lea     rax, WPP_GLOBAL_Control
0x18000b801  cmp     rcx, rax
0x18000b804  jz      short loc_18000B82E
0x18000b806  test    byte ptr [rcx+0E4h], 4
0x18000b80d  jz      short loc_18000B82E
0x18000b80f  cmp     byte ptr [rcx+0E1h], 3
0x18000b816  jb      short loc_18000B82E
0x18000b818  mov     rcx, [rcx+0D8h]
0x18000b81f  lea     edx, [rsi+17h]
0x18000b822  lea     r8, WPP_d9598978672c34cd509ac261b9388a6f_Traceguids
0x18000b829  call    WPP_SF_
0x18000b82e  mov     ebx, 80004003h
0x18000b833  jmp     loc_18000B96A
0x18000b838  mov     dword ptr [rdx], 0FFE00000h
0x18000b83e  xor     r8d, r8d; fWaitAll
0x18000b841  mov     rax, [rcx+18h]
0x18000b845  lea     rdx, [rsp+58h+pHandles]; pHandles
0x18000b84a  mov     [rsp+58h+pHandles], rax
0x18000b84f  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000b853  mov     rax, [rcx+38h]
0x18000b857  mov     ecx, [rcx+40h]
0x18000b85a  mov     [rsp+58h+var_20], rax
0x18000b85f  mov     rax, [rdi+28h]
0x18000b863  mov     [rsp+58h+dwWakeMask], ebx; dwWakeMask
0x18000b867  mov     rcx, [rax+rcx*8]
0x18000b86b  mov     [rsp+58h+var_18], rcx
0x18000b870  lea     ecx, [r8+3]; nCount
0x18000b874  call    cs:__imp_MsgWaitForMultipleObjects
0x18000b87a  mov     r9d, eax
0x18000b87d  test    eax, eax
0x18000b87f  jnz     short loc_18000B8D3
0x18000b881  mov     ebx, 0C0AA0002h
0x18000b886  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b88d  lea     rax, WPP_GLOBAL_Control
0x18000b894  cmp     rcx, rax
0x18000b897  jz      loc_18000B96A
0x18000b89d  test    byte ptr [rcx+0E4h], 4
0x18000b8a4  jz      loc_18000B96A
0x18000b8aa  cmp     byte ptr [rcx+0E1h], 2
0x18000b8b1  jb      loc_18000B96A
0x18000b8b7  lea     edx, [r9+18h]
0x18000b8bb  mov     rcx, [rcx+0D8h]
0x18000b8c2  lea     r8, WPP_d9598978672c34cd509ac261b9388a6f_Traceguids
0x18000b8c9  call    WPP_SF_
0x18000b8ce  jmp     loc_18000B96A
0x18000b8d3  cmp     r9d, 1
0x18000b8d7  jnz     short loc_18000B909
0x18000b8d9  mov     ebx, 0C0AA0002h
0x18000b8de  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8e5  lea     rax, WPP_GLOBAL_Control
0x18000b8ec  cmp     rcx, rax
0x18000b8ef  jz      short loc_18000B96A
0x18000b8f1  test    byte ptr [rcx+0E4h], 4
0x18000b8f8  jz      short loc_18000B96A
0x18000b8fa  cmp     byte ptr [rcx+0E1h], 2
0x18000b901  jb      short loc_18000B96A
0x18000b903  lea     edx, [r9+18h]
0x18000b907  jmp     short loc_18000B8BB
0x18000b909  cmp     r9d, 2
0x18000b90d  jz      short loc_18000B958
0x18000b90f  mov     ebx, 80004005h
0x18000b914  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b91b  lea     rax, WPP_GLOBAL_Control
0x18000b922  cmp     rcx, rax
0x18000b925  jz      short loc_18000B96A
0x18000b927  test    byte ptr [rcx+0E4h], 4
0x18000b92e  jz      short loc_18000B96A
0x18000b930  cmp     byte ptr [rcx+0E1h], 2
0x18000b937  jb      short loc_18000B96A
0x18000b939  mov     rcx, [rcx+0D8h]
0x18000b940  lea     r8, WPP_d9598978672c34cd509ac261b9388a6f_Traceguids
0x18000b947  mov     edx, 1Ah
0x18000b94c  mov     [rsp+58h+dwWakeMask], r9d
0x18000b951  call    WPP_SF_Dd
0x18000b956  jmp     short loc_18000B96A
0x18000b958  mov     ecx, [rdi+40h]
0x18000b95b  xor     edx, edx
0x18000b95d  mov     [rsi], ecx
0x18000b95f  mov     eax, [rdi+40h]
0x18000b962  inc     eax
0x18000b964  div     dword ptr [rdi+20h]
0x18000b967  mov     [rdi+40h], edx
0x18000b96a  mov     eax, ebx
0x18000b96c  mov     rcx, [rsp+58h+var_10]
0x18000b971  xor     rcx, rsp; StackCookie
0x18000b974  call    __security_check_cookie
0x18000b979  mov     rbx, [rsp+58h+arg_10]
0x18000b97e  mov     rsi, [rsp+58h+arg_18]
0x18000b983  add     rsp, 50h
0x18000b987  pop     rdi
0x18000b988  retn
```
