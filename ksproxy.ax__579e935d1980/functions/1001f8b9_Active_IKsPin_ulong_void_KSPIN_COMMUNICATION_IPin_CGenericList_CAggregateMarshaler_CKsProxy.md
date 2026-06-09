# Active(IKsPin *,ulong,void *,KSPIN_COMMUNICATION,IPin *,CGenericList<CAggregateMarshaler> *,CKsProxy *)

- ea: `0x1001f8b9`
- end: `0x1001f9b0`
- name: `?Active@@YGJPAUIKsPin@@KPAXW4KSPIN_COMMUNICATION@@PAUIPin@@PAV?$CGenericList@VCAggregateMarshaler@@@@PAVCKsProxy@@@Z`
- size: `247`
- prototype: `int __userpurge@<eax>(char@<cl>, char, int, int, int, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x10011eb0`
- `0x10015dd0`
- `0x1001b100`

## callees

- `0x10006689`
- `0x1000a7f1`
- `0x1001f16b`
- `0x1001f4ba`
- `0x1001f57f`
- `0x1001f8b9`
- `0x100215e6`
- `0x1002161a`
- `0x10027e56`

## pseudocode

```c
int __fastcall Active(char a1, int a2, int a3, int a4, int a5, int a6, int a7)
{
  PVOID *v8; // eax
  int State; // esi
  int v10; // eax
  void *v12; // [esp+0h] [ebp-14h]
  struct IKsPin *v13; // [esp+0h] [ebp-14h]
  struct IKsPin *v14; // [esp+0h] [ebp-14h]
  void *v15; // [esp+0h] [ebp-14h]
  enum KSSTATE *v16; // [esp+4h] [ebp-10h]
  enum KSSTATE v17; // [esp+4h] [ebp-10h]
  unsigned int v18; // [esp+4h] [ebp-10h]
  enum KSSTATE v19; // [esp+4h] [ebp-10h]
  int v20; // [esp+10h] [ebp-4h]

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_qq(0xEu, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2), a1, a3);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    State = GetState(v12, v16);
    v10 = v20;
    if ( State < 0 && (State != -2147023792 || v20 != 2) )
      return State;
    if ( !v20 )
    {
      State = CKsProxy::PropagateAcquire((CKsProxy *)1, v13, v17);
      FixupPipe(v14, v18);
      if ( State < 0 )
        return State;
      v10 = 0;
    }
    if ( v10 == 2 || (State = SetState(v13, v17), State >= 0) )
    {
      DistributePause(a6);
    }
    else if ( !v20 )
    {
      SetState(v15, v19);
      DistributeStop(a6);
    }
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    State = 0;
  }
  if ( v8 != &WPP_GLOBAL_Control && *((_BYTE *)v8 + 25) >= 2u )
    WPP_SF_qqD(0xFu, *((_QWORD *)v8 + 2), a1, a3, State);
  return State;
}

```

## disassembly

```asm
0x1001f8b9  mov     edi, edi
0x1001f8bb  push    ebp
0x1001f8bc  mov     ebp, esp
0x1001f8be  push    ecx
0x1001f8bf  push    ecx
0x1001f8c0  push    ebx
0x1001f8c1  push    esi; enum KSSTATE
0x1001f8c2  push    edi; void *
0x1001f8c3  mov     [ebp+var_8], edx
0x1001f8c6  mov     ebx, ecx
0x1001f8c8  mov     eax, _WPP_GLOBAL_Control
0x1001f8cd  mov     edi, [ebp+arg_0]
0x1001f8d0  cmp     eax, offset _WPP_GLOBAL_Control
0x1001f8d5  jz      short loc_1001F8F7
0x1001f8d7  cmp     byte ptr [eax+19h], 2
0x1001f8db  jb      short loc_1001F8F7
0x1001f8dd  push    edi; char
0x1001f8de  push    ebx; char
0x1001f8df  push    dword ptr [eax+14h]
0x1001f8e2  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1001f8e7  push    dword ptr [eax+10h]; LoggerHandle
0x1001f8ea  push    0Eh
0x1001f8ec  pop     ecx; MessageNumber
0x1001f8ed  call    _WPP_SF_qq@24; WPP_SF_qq(x,x,x,x,x,x)
0x1001f8f2  mov     eax, _WPP_GLOBAL_Control
0x1001f8f7  test    edi, edi
0x1001f8f9  jz      loc_1001F987
0x1001f8ff  lea     edx, [ebp+var_4]
0x1001f902  mov     ecx, edi
0x1001f904  call    ?GetState@@YGJPAXPAW4KSSTATE@@@Z; GetState(void *,KSSTATE *)
0x1001f909  mov     esi, eax
0x1001f90b  mov     eax, [ebp+var_4]
0x1001f90e  test    esi, esi
0x1001f910  jns     short loc_1001F927
0x1001f912  cmp     esi, 80070450h
0x1001f918  jnz     loc_1001F9A7
0x1001f91e  cmp     eax, 2
0x1001f921  jnz     loc_1001F9A7
0x1001f927  test    eax, eax
0x1001f929  jnz     short loc_1001F94A
0x1001f92b  mov     ecx, [ebp+arg_10]
0x1001f92e  mov     edx, ebx
0x1001f930  push    1; this
0x1001f932  call    ?PropagateAcquire@CKsProxy@@QAGJPAUIKsPin@@K@Z; CKsProxy::PropagateAcquire(IKsPin *,ulong)
0x1001f937  mov     edx, [ebp+var_8]
0x1001f93a  mov     ecx, ebx
0x1001f93c  mov     esi, eax
0x1001f93e  call    ?FixupPipe@@YGJPAUIKsPin@@K@Z; FixupPipe(IKsPin *,ulong)
0x1001f943  test    esi, esi
0x1001f945  js      short loc_1001F9A7
0x1001f947  mov     eax, [ebp+var_4]
0x1001f94a  cmp     eax, 2
0x1001f94d  jz      short loc_1001F978
0x1001f94f  push    2
0x1001f951  pop     edx
0x1001f952  mov     ecx, edi
0x1001f954  call    ?SetState@@YGJPAXW4KSSTATE@@@Z; SetState(void *,KSSTATE)
0x1001f959  mov     esi, eax
0x1001f95b  test    esi, esi
0x1001f95d  jns     short loc_1001F978
0x1001f95f  cmp     [ebp+var_4], 0
0x1001f963  jnz     short loc_1001F980
0x1001f965  xor     edx, edx
0x1001f967  mov     ecx, edi
0x1001f969  call    ?SetState@@YGJPAXW4KSSTATE@@@Z; SetState(void *,KSSTATE)
0x1001f96e  mov     ecx, [ebp+arg_C]
0x1001f971  call    ?DistributeStop@@YGXPAV?$CGenericList@VCAggregateMarshaler@@@@@Z; DistributeStop(CGenericList<CAggregateMarshaler> *)
0x1001f976  jmp     short loc_1001F980
0x1001f978  mov     ecx, [ebp+arg_C]
0x1001f97b  call    ?DistributePause@@YGXPAV?$CGenericList@VCAggregateMarshaler@@@@@Z; DistributePause(CGenericList<CAggregateMarshaler> *)
0x1001f980  mov     eax, _WPP_GLOBAL_Control
0x1001f985  jmp     short loc_1001F989
0x1001f987  xor     esi, esi
0x1001f989  cmp     eax, offset _WPP_GLOBAL_Control
0x1001f98e  jz      short loc_1001F9A7
0x1001f990  cmp     byte ptr [eax+19h], 2
0x1001f994  jb      short loc_1001F9A7
0x1001f996  push    esi; char
0x1001f997  push    edi; char
0x1001f998  push    ebx; char
0x1001f999  push    dword ptr [eax+14h]
0x1001f99c  push    dword ptr [eax+10h]; LoggerHandle
0x1001f99f  push    0Fh
0x1001f9a1  pop     ecx; MessageNumber
0x1001f9a2  call    _WPP_SF_qqD@28; WPP_SF_qqD(x,x,x,x,x,x,x)
0x1001f9a7  pop     edi
0x1001f9a8  mov     eax, esi
0x1001f9aa  pop     esi
0x1001f9ab  pop     ebx
0x1001f9ac  leave
0x1001f9ad  retn    14h
```
