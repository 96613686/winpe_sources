# CBTreeIterator::Next(char * *,ulong *)

- ea: `0x18000dc00`
- end: `0x18000dee7`
- name: `?Next@CBTreeIterator@@QEAAKPEAPEADPEAK@Z`
- size: `743`
- prototype: `unsigned int __fastcall(CBTreeIterator *__hidden this, char **, unsigned int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c500`
- `0x18000cb50`
- `0x180028a74`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18000d7e0`
- `0x18000dc00`
- `0x18000eee0`
- `0x18000fb70`
- `0x180010fa0`
- `0x1800129a0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18000dd24`
- `wbemcomn!GetMemLogObject` at `0x18000ddc3`
- `wbemcomn!GetMemLogObject` at `0x18000de14`
- `wbemcomn!GetMemLogObject` at `0x18000de65`
- `wbemcomn!GetMemLogObject` at `0x18000dd24`
- `wbemcomn!GetMemLogObject` at `0x18000ddc3`
- `wbemcomn!GetMemLogObject` at `0x18000de14`
- `wbemcomn!GetMemLogObject` at `0x18000de65`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000dd2f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ddd1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000de1f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000de73`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000dd2f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000ddd1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000de1f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000de73`

## pseudocode

```c
__int64 __fastcall CBTreeIterator::Next(CBTreeIterator *this, char **a2, SIdxKeyTable *a3)
{
  __int64 v5; // rdx
  SIdxKeyTable *v6; // rcx
  unsigned int KeyAt; // esi
  __int64 v8; // r8
  unsigned int i; // edx
  __int64 j; // rcx
  CBTree *v12; // rcx
  CMemoryLog *v13; // rax
  CVarObjHeap *v14; // rcx
  __int64 v15; // rcx
  SIdxKeyTable *v16; // rdx
  CMemoryLog *v17; // rax
  CMemoryLog *MemLogObject; // rax
  __int64 v19; // rdx
  SIdxKeyTable *v20; // rcx
  CMemoryLog *v21; // rax
  SIdxKeyTable *v22; // [rsp+50h] [rbp+18h] BYREF

  v22 = a3;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 188, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids);
  }
  if ( a2 )
  {
    *a2 = 0;
    v5 = *((int *)this + 2562);
    v6 = (SIdxKeyTable *)*((_QWORD *)this + v5 + 1);
    if ( v6 )
    {
      KeyAt = SIdxKeyTable::GetKeyAt(v6, *((_WORD *)this + v5 + 4100), a2);
      if ( KeyAt )
      {
        MemLogObject = GetMemLogObject();
        CMemoryLog::Write(MemLogObject, KeyAt);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = 190;
LABEL_39:
          WPP_SF_d(*((_QWORD *)v14 + 2), v19, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, KeyAt);
        }
      }
      else
      {
        for ( i = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + *((int *)this + 2562) + 1) + 40LL)
                            + 4LL * (unsigned __int16)++*((_WORD *)this + *((int *)this + 2562) + 4100));
              ;
              i = **((_DWORD **)v16 + 5) )
        {
          if ( i == -1 )
          {
            for ( j = *((int *)this + 2562); *((_QWORD *)this + j + 1); j = *((int *)this + 2562) )
            {
              if ( *((_WORD *)this + (int)j + 4100) != *(_WORD *)(*((_QWORD *)this + (int)j + 1) + 12LL) )
                break;
              CBTreeIterator::Pop(this);
            }
            return 0;
          }
          v12 = *(CBTree **)this;
          LOBYTE(v8) = 1;
          v22 = 0;
          KeyAt = CBTree::ReadIdxPage(v12, i, v8, &v22);
          if ( KeyAt )
            break;
          v15 = *((int *)this + 2562);
          if ( (_DWORD)v15 == 1023 )
          {
            _BtrMemFree(*a2);
            v20 = v22;
            *a2 = 0;
            SIdxKeyTable::Release(v20);
            v21 = GetMemLogObject();
            CMemoryLog::Write(v21, 122);
            if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 192, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 122);
            }
            return 122;
          }
          v16 = v22;
          *((_DWORD *)this + 2562) = v15 + 1;
          *((_QWORD *)this + v15 + 2) = v16;
          *((_WORD *)this + *((int *)this + 2562) + 4100) = 0;
        }
        _BtrMemFree(*a2);
        *a2 = 0;
        v13 = GetMemLogObject();
        CMemoryLog::Write(v13, KeyAt);
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = 191;
          goto LABEL_39;
        }
      }
      return KeyAt;
    }
    else
    {
      return 259;
    }
  }
  else
  {
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, 87);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids, 87);
    }
    return 87;
  }
}

```

## disassembly

```asm
0x18000dc00  mov     [rsp+arg_10], r8
0x18000dc05  push    rbx
0x18000dc06  push    rdi
0x18000dc07  push    r14
0x18000dc09  sub     rsp, 20h
0x18000dc0d  mov     rdi, rdx
0x18000dc10  mov     rbx, rcx
0x18000dc13  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc1a  lea     r14, WPP_GLOBAL_Control
0x18000dc21  cmp     rcx, r14
0x18000dc24  jz      short loc_18000DC30
0x18000dc26  test    byte ptr [rcx+1Ch], 1
0x18000dc2a  jnz     loc_18000DD9F
0x18000dc30  test    rdi, rdi
0x18000dc33  jz      loc_18000DDC3
0x18000dc39  mov     [rsp+38h+arg_0], rbp
0x18000dc3e  xor     ebp, ebp
0x18000dc40  mov     [rdi], rbp
0x18000dc43  movsxd  rdx, dword ptr [rbx+2808h]
0x18000dc4a  mov     rcx, [rbx+rdx*8+8]; this
0x18000dc4f  test    rcx, rcx
0x18000dc52  jz      loc_18000DD4C
0x18000dc58  movzx   edx, word ptr [rbx+rdx*2+2008h]; unsigned __int16
0x18000dc60  mov     r8, rdi; char **
0x18000dc63  mov     [rsp+38h+arg_8], rsi
0x18000dc68  call    ?GetKeyAt@SIdxKeyTable@@QEAAKGPEAPEAD@Z; SIdxKeyTable::GetKeyAt(ushort,char * *)
0x18000dc6d  mov     esi, eax
0x18000dc6f  test    eax, eax
0x18000dc71  jnz     loc_18000DE14
0x18000dc77  movsxd  rax, dword ptr [rbx+2808h]
0x18000dc7e  inc     word ptr [rbx+rax*2+2008h]
0x18000dc86  movsxd  rax, dword ptr [rbx+2808h]
0x18000dc8d  movzx   edx, word ptr [rbx+rax*2+2008h]
0x18000dc95  mov     rax, [rbx+rax*8+8]
0x18000dc9a  mov     rcx, [rax+28h]
0x18000dc9e  mov     edx, [rcx+rdx*4]; unsigned int
0x18000dca1  cmp     edx, 0FFFFFFFFh
0x18000dca4  jnz     short loc_18000DCFE
0x18000dca6  movsxd  rcx, dword ptr [rbx+2808h]
0x18000dcad  cmp     [rbx+rcx*8+8], rbp
0x18000dcb2  jnz     short loc_18000DCD0
0x18000dcb4  xor     eax, eax
0x18000dcb6  mov     rsi, [rsp+38h+arg_8]
0x18000dcbb  mov     rbp, [rsp+38h+arg_0]
0x18000dcc0  add     rsp, 20h
0x18000dcc4  pop     r14
0x18000dcc6  pop     rdi
0x18000dcc7  pop     rbx
0x18000dcc8  retn
0x18000dcd0  movsxd  rdx, ecx
0x18000dcd3  mov     rax, [rbx+rdx*8+8]
0x18000dcd8  movzx   ecx, word ptr [rax+0Ch]
0x18000dcdc  cmp     [rbx+rdx*2+2008h], cx
0x18000dce4  jnz     short loc_18000DCB4
0x18000dce6  mov     rcx, rbx; this
0x18000dce9  call    ?Pop@CBTreeIterator@@AEAAXXZ; CBTreeIterator::Pop(void)
0x18000dcee  movsxd  rcx, dword ptr [rbx+2808h]
0x18000dcf5  cmp     [rbx+rcx*8+8], rbp
0x18000dcfa  jnz     short loc_18000DCD0
0x18000dcfc  jmp     short loc_18000DCB4
0x18000dcfe  mov     rcx, [rbx]; this
0x18000dd01  lea     r9, [rsp+38h+arg_10]; struct SIdxKeyTable **
0x18000dd06  mov     r8b, 1; bool
0x18000dd09  mov     [rsp+38h+arg_10], rbp
0x18000dd0e  call    ?ReadIdxPage@CBTree@@AEAAKK_NPEAPEAVSIdxKeyTable@@@Z; CBTree::ReadIdxPage(ulong,bool,SIdxKeyTable * *)
0x18000dd13  mov     esi, eax
0x18000dd15  test    eax, eax
0x18000dd17  jz      short loc_18000DD5F
0x18000dd19  mov     rcx, [rdi]; void *
0x18000dd1c  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x18000dd21  mov     [rdi], rbp
0x18000dd24  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000dd2a  mov     rcx, rax
0x18000dd2d  mov     edx, esi
0x18000dd2f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000dd35  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd3c  cmp     rcx, r14
0x18000dd3f  jnz     loc_18000DEB6
0x18000dd45  mov     eax, esi
0x18000dd47  jmp     loc_18000DCB6
0x18000dd4c  mov     rbp, [rsp+38h+arg_0]
0x18000dd51  mov     eax, 103h
0x18000dd56  add     rsp, 20h
0x18000dd5a  pop     r14
0x18000dd5c  pop     rdi
0x18000dd5d  pop     rbx
0x18000dd5e  retn
0x18000dd5f  movsxd  rcx, dword ptr [rbx+2808h]
0x18000dd66  cmp     ecx, 3FFh
0x18000dd6c  jz      loc_18000DE50
0x18000dd72  mov     rdx, [rsp+38h+arg_10]
0x18000dd77  lea     eax, [rcx+1]
0x18000dd7a  mov     [rbx+2808h], eax
0x18000dd80  mov     [rbx+rcx*8+10h], rdx
0x18000dd85  movsxd  rcx, dword ptr [rbx+2808h]
0x18000dd8c  mov     [rbx+rcx*2+2008h], bp
0x18000dd94  mov     rax, [rdx+28h]
0x18000dd98  mov     edx, [rax]
0x18000dd9a  jmp     loc_18000DCA1
0x18000dd9f  cmp     byte ptr [rcx+19h], 5
0x18000dda3  jb      loc_18000DC30
0x18000dda9  mov     rcx, [rcx+10h]
0x18000ddad  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000ddb4  mov     edx, 0BCh
0x18000ddb9  call    WPP_SF_
0x18000ddbe  jmp     loc_18000DC30
0x18000ddc3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000ddc9  mov     rcx, rax
0x18000ddcc  mov     edx, 57h ; 'W'
0x18000ddd1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000ddd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddde  cmp     rcx, r14
0x18000dde1  jz      short loc_18000DE0A
0x18000dde3  test    byte ptr [rcx+1Ch], 1
0x18000dde7  jz      short loc_18000DE0A
0x18000dde9  cmp     byte ptr [rcx+19h], 2
0x18000dded  jb      short loc_18000DE0A
0x18000ddef  mov     rcx, [rcx+10h]
0x18000ddf3  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000ddfa  mov     edx, 0BDh
0x18000ddff  mov     r9d, 57h ; 'W'
0x18000de05  call    WPP_SF_d
0x18000de0a  mov     eax, 57h ; 'W'
0x18000de0f  jmp     loc_18000DCC0
0x18000de14  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000de1a  mov     rcx, rax
0x18000de1d  mov     edx, esi
0x18000de1f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000de25  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de2c  cmp     rcx, r14
0x18000de2f  jz      loc_18000DD45
0x18000de35  test    byte ptr [rcx+1Ch], 1
0x18000de39  jz      loc_18000DD45
0x18000de3f  cmp     byte ptr [rcx+19h], 2
0x18000de43  jb      loc_18000DD45
0x18000de49  mov     edx, 0BEh
0x18000de4e  jmp     short loc_18000DECF
0x18000de50  mov     rcx, [rdi]; void *
0x18000de53  call    ?_BtrMemFree@@YAHPEAX@Z; _BtrMemFree(void *)
0x18000de58  mov     rcx, [rsp+38h+arg_10]; this
0x18000de5d  mov     [rdi], rbp
0x18000de60  call    ?Release@SIdxKeyTable@@QEAAKXZ; SIdxKeyTable::Release(void)
0x18000de65  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000de6b  mov     rcx, rax
0x18000de6e  mov     edx, 7Ah ; 'z'
0x18000de73  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000de79  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de80  cmp     rcx, r14
0x18000de83  jz      short loc_18000DEAC
0x18000de85  test    byte ptr [rcx+1Ch], 1
0x18000de89  jz      short loc_18000DEAC
0x18000de8b  cmp     byte ptr [rcx+19h], 2
0x18000de8f  jb      short loc_18000DEAC
0x18000de91  mov     rcx, [rcx+10h]
0x18000de95  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000de9c  mov     edx, 0C0h
0x18000dea1  mov     r9d, 7Ah ; 'z'
0x18000dea7  call    WPP_SF_d
0x18000deac  mov     eax, 7Ah ; 'z'
0x18000deb1  jmp     loc_18000DCB6
0x18000deb6  test    byte ptr [rcx+1Ch], 1
0x18000deba  jz      loc_18000DD45
0x18000dec0  cmp     byte ptr [rcx+19h], 2
0x18000dec4  jb      loc_18000DD45
0x18000deca  mov     edx, 0BFh
0x18000decf  mov     rcx, [rcx+10h]
0x18000ded3  lea     r8, WPP_ef29f003c98a3d19744f3b0aa76ea2fb_Traceguids
0x18000deda  mov     r9d, esi
0x18000dedd  call    WPP_SF_d
0x18000dee2  jmp     loc_18000DD45
```
