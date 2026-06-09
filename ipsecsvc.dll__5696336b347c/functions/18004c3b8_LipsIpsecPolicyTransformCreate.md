# LipsIpsecPolicyTransformCreate

- ea: `0x18004c3b8`
- end: `0x18004c527`
- name: `LipsIpsecPolicyTransformCreate`
- size: `367`
- prototype: `__int64 __fastcall(_DWORD *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004c530`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x18004bc80`
- `0x18004bed8`
- `0x18004bfbc`
- `0x18004c094`
- `0x18004c3b8`

## string_xrefs

- `0x18004c50f`: `LipsIpsecPolicyTransformCreate`

## pseudocode

```c
__int64 __fastcall LipsIpsecPolicyTransformCreate(_DWORD *a1, __int64 a2)
{
  unsigned int v2; // ebx
  int v3; // r8d
  BOOL v4; // r9d
  int v5; // r10d
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  int v8; // r11d
  _DWORD *v9; // rax

  v2 = 0;
  v3 = 1;
  if ( *a1 != 1 )
  {
    if ( *a1 != 2 )
      return v2;
    v8 = a1[1];
    v9 = a1 + 2;
    if ( v8 )
    {
      v4 = 0;
      if ( !*v9 )
      {
        v5 = 1;
        goto LABEL_14;
      }
    }
    else
    {
      v4 = *v9 != 0;
    }
    v5 = 0;
    if ( v8 && *v9 )
    {
LABEL_15:
      if ( v4 )
      {
        v2 = LipsIpsecPolicyEspAuthCreate((__int64)a1, (_DWORD *)a2, (_QWORD *)(a2 + 8));
        if ( v2 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            return (unsigned int)LipsReportError(v2, "LipsIpsecPolicyTransformCreate");
          }
          v7 = 18;
LABEL_32:
          WPP_SF_d(v6[2], v7, WPP_27bbdfd7f9373f774044576864095fd9_Traceguids, v2);
          return (unsigned int)LipsReportError(v2, "LipsIpsecPolicyTransformCreate");
        }
      }
      else if ( v5 )
      {
        v2 = LipsIpsecPolicyEspCipherCreate((__int64)a1, (_DWORD *)a2, (_QWORD *)(a2 + 8));
        if ( v2 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            return (unsigned int)LipsReportError(v2, "LipsIpsecPolicyTransformCreate");
          }
          v7 = 19;
          goto LABEL_32;
        }
      }
      else if ( v3 )
      {
        v2 = LipsIpsecPolicyEspAuthCipherCreate((__int64)a1, (_DWORD *)a2, (__int64 *)(a2 + 8));
        if ( v2 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
          {
            return (unsigned int)LipsReportError(v2, "LipsIpsecPolicyTransformCreate");
          }
          v7 = 20;
          goto LABEL_32;
        }
      }
      return v2;
    }
LABEL_14:
    v3 = 0;
    goto LABEL_15;
  }
  if ( !a1[1] || a1[2] )
  {
    v4 = 0;
    v5 = 0;
    goto LABEL_14;
  }
  v2 = LipsIpsecPolicyAhCreate((__int64)a1, (_DWORD *)a2, (_QWORD *)(a2 + 8));
  if ( v2 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      return (unsigned int)LipsReportError(v2, "LipsIpsecPolicyTransformCreate");
    v7 = 17;
    goto LABEL_32;
  }
  return v2;
}

```

## disassembly

```asm
0x18004c3b8  push    rbx
0x18004c3ba  sub     rsp, 20h
0x18004c3be  xor     ebx, ebx
0x18004c3c0  lea     r8d, [rbx+1]
0x18004c3c4  cmp     [rcx], r8d
0x18004c3c7  jnz     short loc_18004C419
0x18004c3c9  cmp     [rcx+4], ebx
0x18004c3cc  jz      short loc_18004C3D3
0x18004c3ce  cmp     [rcx+8], ebx
0x18004c3d1  jz      short loc_18004C3DB
0x18004c3d3  xor     r9d, r9d
0x18004c3d6  xor     r10d, r10d
0x18004c3d9  jmp     short loc_18004C442
0x18004c3db  lea     r8, [rdx+8]
0x18004c3df  call    LipsIpsecPolicyAhCreate
0x18004c3e4  mov     ebx, eax
0x18004c3e6  test    eax, eax
0x18004c3e8  jz      loc_18004C51F
0x18004c3ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c3f5  lea     rax, WPP_GLOBAL_Control
0x18004c3fc  cmp     rcx, rax
0x18004c3ff  jz      loc_18004C50F
0x18004c405  test    byte ptr [rcx+1Ch], 10h
0x18004c409  jz      loc_18004C50F
0x18004c40f  mov     edx, 11h
0x18004c414  jmp     loc_18004C4FC
0x18004c419  cmp     dword ptr [rcx], 2
0x18004c41c  jnz     loc_18004C51F
0x18004c422  mov     r11d, [rcx+4]
0x18004c426  lea     rax, [rcx+8]
0x18004c42a  test    r11d, r11d
0x18004c42d  jnz     short loc_18004C48A
0x18004c42f  cmp     [rax], ebx
0x18004c431  jz      short loc_18004C485
0x18004c433  mov     r9d, r8d
0x18004c436  xor     r10d, r10d
0x18004c439  test    r11d, r11d
0x18004c43c  jz      short loc_18004C442
0x18004c43e  cmp     [rax], ebx
0x18004c440  jnz     short loc_18004C445
0x18004c442  xor     r8d, r8d
0x18004c445  test    r9d, r9d
0x18004c448  jz      short loc_18004C496
0x18004c44a  lea     r8, [rdx+8]
0x18004c44e  call    LipsIpsecPolicyEspAuthCreate
0x18004c453  mov     ebx, eax
0x18004c455  test    eax, eax
0x18004c457  jz      loc_18004C51F
0x18004c45d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c464  lea     rax, WPP_GLOBAL_Control
0x18004c46b  cmp     rcx, rax
0x18004c46e  jz      loc_18004C50F
0x18004c474  test    byte ptr [rcx+1Ch], 10h
0x18004c478  jz      loc_18004C50F
0x18004c47e  mov     edx, 12h
0x18004c483  jmp     short loc_18004C4FC
0x18004c485  xor     r9d, r9d
0x18004c488  jmp     short loc_18004C436
0x18004c48a  xor     r9d, r9d
0x18004c48d  cmp     [rax], ebx
0x18004c48f  jnz     short loc_18004C436
0x18004c491  mov     r10d, r8d
0x18004c494  jmp     short loc_18004C442
0x18004c496  test    r10d, r10d
0x18004c499  jz      short loc_18004C4CA
0x18004c49b  lea     r8, [rdx+8]
0x18004c49f  call    LipsIpsecPolicyEspCipherCreate
0x18004c4a4  mov     ebx, eax
0x18004c4a6  test    eax, eax
0x18004c4a8  jz      short loc_18004C51F
0x18004c4aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c4b1  lea     rax, WPP_GLOBAL_Control
0x18004c4b8  cmp     rcx, rax
0x18004c4bb  jz      short loc_18004C50F
0x18004c4bd  test    byte ptr [rcx+1Ch], 10h
0x18004c4c1  jz      short loc_18004C50F
0x18004c4c3  mov     edx, 13h
0x18004c4c8  jmp     short loc_18004C4FC
0x18004c4ca  test    r8d, r8d
0x18004c4cd  jz      short loc_18004C51F
0x18004c4cf  lea     r8, [rdx+8]
0x18004c4d3  call    LipsIpsecPolicyEspAuthCipherCreate
0x18004c4d8  mov     ebx, eax
0x18004c4da  test    eax, eax
0x18004c4dc  jz      short loc_18004C51F
0x18004c4de  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c4e5  lea     rax, WPP_GLOBAL_Control
0x18004c4ec  cmp     rcx, rax
0x18004c4ef  jz      short loc_18004C50F
0x18004c4f1  test    byte ptr [rcx+1Ch], 10h
0x18004c4f5  jz      short loc_18004C50F
0x18004c4f7  mov     edx, 14h
0x18004c4fc  mov     rcx, [rcx+10h]
0x18004c500  lea     r8, WPP_27bbdfd7f9373f774044576864095fd9_Traceguids
0x18004c507  mov     r9d, ebx
0x18004c50a  call    WPP_SF_d
0x18004c50f  lea     rdx, aLipsipsecpolic_0; "LipsIpsecPolicyTransformCreate"
0x18004c516  mov     ecx, ebx
0x18004c518  call    LipsReportError
0x18004c51d  mov     ebx, eax
0x18004c51f  mov     eax, ebx
0x18004c521  add     rsp, 20h
0x18004c525  pop     rbx
0x18004c526  retn
```
