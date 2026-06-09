# WimQueryAutoConfigParameter(_DOT3_AUTOCONF_OPCODE,int,ulong *,uchar * *,_DOT3_OPCODE_VALUE_TYPE *)

- ea: `0x1800113f0`
- end: `0x180011631`
- name: `?WimQueryAutoConfigParameter@@YAKW4_DOT3_AUTOCONF_OPCODE@@HPEAKPEAPEAEPEAW4_DOT3_OPCODE_VALUE_TYPE@@@Z`
- size: `577`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180020574`

## callees

- `0x18000a7ec`
- `0x18000a87c`
- `0x18000a9c0`
- `0x18000c230`
- `0x18000f440`
- `0x18000f47c`
- `0x1800113f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001146e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001152f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001146e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001152f`

## pseudocode

```c
__int64 __fastcall WimQueryAutoConfigParameter(int a1, __int64 a2, _DWORD *a3, _QWORD *a4, int *a5)
{
  int v7; // ebp
  unsigned int v9; // edi
  struct _LIST_ENTRY *v10; // rcx
  int v11; // ebx
  _DWORD *v12; // rbx
  DWORD LastError; // eax
  __int64 v14; // rdx
  int v15; // eax
  int v16; // esi

  v7 = a2;
  v9 = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 130, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  v11 = a1 - 1;
  if ( !v11 )
  {
    v12 = Dot3Alloc(4u, a2, (__int64)a3);
    if ( !v12 )
    {
      LastError = GetLastError();
      v9 = LastError;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v9;
      if ( !BYTE1(WPP_GLOBAL_Control[1].Blink) || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        goto LABEL_42;
      v14 = 131;
      goto LABEL_13;
    }
    if ( !v7 || (v9 = LockLanIntfmgrState((struct LAN_INTFMGR_CONTEXT *)&g_IntfMgrContext)) == 0 )
    {
      if ( dword_180052E78 && (BYTE4(xmmword_180052E7C) & 1) != 0 )
      {
        v15 = DWORD2(xmmword_180052E7C) == 0;
        goto LABEL_33;
      }
      v15 = qword_180052EB8 != 0;
      goto LABEL_35;
    }
LABEL_29:
    Dot3Free(v12);
LABEL_41:
    v10 = WPP_GLOBAL_Control;
    goto LABEL_42;
  }
  if ( v11 != 1 )
  {
    v9 = 87;
    goto LABEL_42;
  }
  v12 = Dot3Alloc(4u, a2, (__int64)a3);
  if ( v12 )
  {
    if ( !v7 || (v9 = LockLanIntfmgrState((struct LAN_INTFMGR_CONTEXT *)&g_IntfMgrContext)) == 0 )
    {
      if ( dword_180052E78 )
      {
        if ( (BYTE12(xmmword_180052E7C) & 1) != 0 )
        {
          v15 = dword_180052E8C;
LABEL_33:
          v16 = 1;
LABEL_36:
          *v12 = v15;
          goto LABEL_37;
        }
LABEL_21:
        v16 = 0;
        *v12 = -1;
LABEL_37:
        if ( v7 )
          UnlockLanIntfmgrState((struct LAN_INTFMGR_CONTEXT *)&g_IntfMgrContext);
        *a3 = 4;
        *a4 = v12;
        if ( a5 )
          *a5 = v16;
        goto LABEL_41;
      }
      if ( !HIDWORD(qword_180052EB8) )
        goto LABEL_21;
      v15 = dword_180052EC0;
LABEL_35:
      v16 = 2;
      goto LABEL_36;
    }
    goto LABEL_29;
  }
  LastError = GetLastError();
  v9 = LastError;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v9;
  if ( BYTE1(WPP_GLOBAL_Control[1].Blink) && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    v14 = 132;
LABEL_13:
    WPP_SF_d(v10[1].Flink, v14, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids, LastError);
    v10 = WPP_GLOBAL_Control;
  }
LABEL_42:
  if ( v10 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v10[1].Blink) >= 4u && (BYTE4(v10[1].Blink) & 1) != 0 )
    WPP_SF_d(v10[1].Flink, 133, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x1800113f0  push    rbx
0x1800113f2  push    rbp
0x1800113f3  push    rsi
0x1800113f4  push    rdi
0x1800113f5  push    r14
0x1800113f7  push    r15
0x1800113f9  sub     rsp, 28h
0x1800113fd  mov     r14, r9
0x180011400  mov     r15, r8
0x180011403  mov     ebp, edx
0x180011405  mov     ebx, ecx
0x180011407  xor     edi, edi
0x180011409  mov     rcx, cs:WPP_GLOBAL_Control
0x180011410  lea     rax, WPP_GLOBAL_Control
0x180011417  cmp     rcx, rax
0x18001141a  jz      short loc_180011444
0x18001141c  cmp     byte ptr [rcx+19h], 4
0x180011420  jb      short loc_180011444
0x180011422  test    byte ptr [rcx+1Ch], 1
0x180011426  jz      short loc_180011444
0x180011428  mov     rcx, [rcx+10h]
0x18001142c  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x180011433  mov     edx, 82h
0x180011438  call    WPP_SF_
0x18001143d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011444  sub     ebx, 1
0x180011447  jz      loc_18001151D
0x18001144d  cmp     ebx, 1
0x180011450  jz      short loc_18001145C
0x180011452  mov     edi, 57h ; 'W'
0x180011457  jmp     loc_1800115F2
0x18001145c  mov     ecx, 4; dwBytes
0x180011461  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x180011466  mov     rbx, rax
0x180011469  test    rax, rax
0x18001146c  jnz     short loc_1800114C5
0x18001146e  call    cs:__imp_GetLastError
0x180011474  mov     edi, eax
0x180011476  mov     rcx, cs:WPP_GLOBAL_Control
0x18001147d  lea     rbx, WPP_GLOBAL_Control
0x180011484  cmp     rcx, rbx
0x180011487  jz      loc_180011622
0x18001148d  cmp     byte ptr [rcx+19h], 1
0x180011491  jb      loc_1800115F9
0x180011497  test    byte ptr [rcx+1Ch], 1
0x18001149b  jz      loc_1800115F9
0x1800114a1  mov     edx, 84h
0x1800114a6  mov     rcx, [rcx+10h]
0x1800114aa  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x1800114b1  mov     r9d, eax
0x1800114b4  call    WPP_SF_d
0x1800114b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800114c0  jmp     loc_1800115F9
0x1800114c5  test    ebp, ebp
0x1800114c7  jz      short loc_1800114DF
0x1800114c9  lea     rcx, ?g_IntfMgrContext@@3ULAN_INTFMGR_CONTEXT@@A; struct LAN_INTFMGR_CONTEXT *
0x1800114d0  call    ?LockLanIntfmgrState@@YAKAEAULAN_INTFMGR_CONTEXT@@@Z; LockLanIntfmgrState(LAN_INTFMGR_CONTEXT &)
0x1800114d5  mov     edi, eax
0x1800114d7  test    eax, eax
0x1800114d9  jnz     loc_180011582
0x1800114df  cmp     cs:dword_180052E78, 0
0x1800114e6  jz      short loc_1800114FC
0x1800114e8  test    byte ptr cs:xmmword_180052E7C+0Ch, 1
0x1800114ef  jz      short loc_180011510
0x1800114f1  mov     eax, cs:dword_180052E8C
0x1800114f7  jmp     loc_1800115A9
0x1800114fc  cmp     dword ptr cs:qword_180052EB8+4, 0
0x180011503  jz      short loc_180011510
0x180011505  mov     eax, cs:dword_180052EC0
0x18001150b  jmp     loc_1800115BB
0x180011510  xor     esi, esi
0x180011512  mov     dword ptr [rbx], 0FFFFFFFFh
0x180011518  jmp     loc_1800115C2
0x18001151d  mov     ecx, 4; dwBytes
0x180011522  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x180011527  mov     rbx, rax
0x18001152a  test    rax, rax
0x18001152d  jnz     short loc_18001156C
0x18001152f  call    cs:__imp_GetLastError
0x180011535  mov     edi, eax
0x180011537  mov     rcx, cs:WPP_GLOBAL_Control
0x18001153e  lea     rbx, WPP_GLOBAL_Control
0x180011545  cmp     rcx, rbx
0x180011548  jz      loc_180011622
0x18001154e  cmp     byte ptr [rcx+19h], 1
0x180011552  jb      loc_1800115F9
0x180011558  test    byte ptr [rcx+1Ch], 1
0x18001155c  jz      loc_1800115F9
0x180011562  mov     edx, 83h
0x180011567  jmp     loc_1800114A6
0x18001156c  test    ebp, ebp
0x18001156e  jz      short loc_18001158C
0x180011570  lea     rcx, ?g_IntfMgrContext@@3ULAN_INTFMGR_CONTEXT@@A; struct LAN_INTFMGR_CONTEXT *
0x180011577  call    ?LockLanIntfmgrState@@YAKAEAULAN_INTFMGR_CONTEXT@@@Z; LockLanIntfmgrState(LAN_INTFMGR_CONTEXT &)
0x18001157c  mov     edi, eax
0x18001157e  test    eax, eax
0x180011580  jz      short loc_18001158C
0x180011582  mov     rcx, rbx; lpMem
0x180011585  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x18001158a  jmp     short loc_1800115EB
0x18001158c  cmp     cs:dword_180052E78, 0
0x180011593  jz      short loc_1800115B0
0x180011595  test    byte ptr cs:xmmword_180052E7C+4, 1
0x18001159c  jz      short loc_1800115B0
0x18001159e  xor     eax, eax
0x1800115a0  cmp     dword ptr cs:xmmword_180052E7C+8, eax
0x1800115a6  setz    al
0x1800115a9  mov     esi, 1
0x1800115ae  jmp     short loc_1800115C0
0x1800115b0  xor     eax, eax
0x1800115b2  cmp     dword ptr cs:qword_180052EB8, eax
0x1800115b8  setnz   al
0x1800115bb  mov     esi, 2
0x1800115c0  mov     [rbx], eax
0x1800115c2  test    ebp, ebp
0x1800115c4  jz      short loc_1800115D2
0x1800115c6  lea     rcx, ?g_IntfMgrContext@@3ULAN_INTFMGR_CONTEXT@@A; struct LAN_INTFMGR_CONTEXT *
0x1800115cd  call    ?UnlockLanIntfmgrState@@YAXAEAULAN_INTFMGR_CONTEXT@@@Z; UnlockLanIntfmgrState(LAN_INTFMGR_CONTEXT &)
0x1800115d2  mov     rax, [rsp+58h+arg_20]
0x1800115da  mov     dword ptr [r15], 4
0x1800115e1  mov     [r14], rbx
0x1800115e4  test    rax, rax
0x1800115e7  jz      short loc_1800115EB
0x1800115e9  mov     [rax], esi
0x1800115eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115f2  lea     rbx, WPP_GLOBAL_Control
0x1800115f9  cmp     rcx, rbx
0x1800115fc  jz      short loc_180011622
0x1800115fe  cmp     byte ptr [rcx+19h], 4
0x180011602  jb      short loc_180011622
0x180011604  test    byte ptr [rcx+1Ch], 1
0x180011608  jz      short loc_180011622
0x18001160a  mov     rcx, [rcx+10h]
0x18001160e  lea     r8, WPP_41caf6f8117b3ad837214700da2680fc_Traceguids
0x180011615  mov     edx, 85h
0x18001161a  mov     r9d, edi
0x18001161d  call    WPP_SF_d
0x180011622  mov     eax, edi
0x180011624  add     rsp, 28h
0x180011628  pop     r15
0x18001162a  pop     r14
0x18001162c  pop     rdi
0x18001162d  pop     rsi
0x18001162e  pop     rbp
0x18001162f  pop     rbx
0x180011630  retn
```
