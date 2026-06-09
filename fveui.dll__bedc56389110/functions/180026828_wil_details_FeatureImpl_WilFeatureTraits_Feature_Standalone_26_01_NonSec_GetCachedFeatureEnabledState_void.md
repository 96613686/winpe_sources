# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180026828`
- end: `0x180026980`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `344`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800274f8`

## callees

- `0x1800086f8`
- `0x18000bb98`
- `0x18002331c`
- `0x180026828`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  int *v6; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v8; // r8d
  int v9; // edi
  int v10; // eax
  int v11; // edi
  int v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  signed __int32 v15; // ecx
  wil::details *v17; // [rsp+40h] [rbp+8h] BYREF

  v17 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x37E286C,
                            3u,
                            (enum FEATURE_CHANGE_TIME)&v17,
                            v6);
    v8 = FeatureEnabledState & 0xFFFFFF3F;
    v9 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
    }
    else
    {
      v10 = 64;
    }
    v11 = v10 | v9;
    v12 = *(_DWORD *)a2;
    do
    {
      v13 = (_DWORD)v17 == 0;
      v14 = v12;
      *(_DWORD *)a2 = v12;
      if ( !v13 && (v12 & 2) == 0 )
      {
        v12 = (v12
             ^ ((unsigned __int16)v12
              ^ (unsigned __int16)v11)
             & 0x180
             ^ (v11
              ^ v12
              ^ ((unsigned __int16)v12
               ^ (unsigned __int16)v11)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v11
             ^ ((unsigned __int16)(v12 ^ (v12 ^ v11) & 0x180 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v12;
      }
      if ( (v14 & 4) != 0 )
      {
        v15 = v12;
      }
      else
      {
        v15 = v12 ^ ((unsigned __int16)v12 ^ (unsigned __int16)v11) & 0x400 | 4;
        *(_DWORD *)a2 = v15;
      }
      v12 = _InterlockedCompareExchange(
              (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_01_NonSec__descriptor, 3, v5);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v11
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v11
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v11
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v11
                        ^ (unsigned __int16)*(_DWORD *)a2)
                       & 0x180)
                      & 0x40
                      | 1))
                    & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x180026828  mov     [rsp+arg_8], rbx
0x18002682d  mov     [rsp+arg_10], rbp
0x180026832  mov     [rsp+arg_0], rcx
0x180026837  push    rsi
0x180026838  push    rdi
0x180026839  push    r15
0x18002683b  sub     rsp, 20h
0x18002683f  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180026846  mov     rbx, rdx
0x180026849  mov     qword ptr [rdx], 0
0x180026850  mov     eax, [rsi]
0x180026852  mov     [rdx], eax
0x180026854  and     eax, 6
0x180026857  cmp     al, 6
0x180026859  jz      loc_18002696A
0x18002685f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180026864  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180026869  mov     dword ptr [rsp+38h+arg_0], 0
0x180026871  mov     edx, 3; unsigned int
0x180026876  mov     ecx, 37E286Ch; this
0x18002687b  mov     ebp, eax
0x18002687d  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180026882  mov     r8d, eax
0x180026885  mov     ecx, eax
0x180026887  and     r8d, 0FFFFFF3Fh
0x18002688e  and     eax, 80h
0x180026893  mov     edx, r8d
0x180026896  mov     r15d, 40h ; '@'
0x18002689c  and     edx, 3
0x18002689f  and     ecx, r15d
0x1800268a2  shl     edx, 2
0x1800268a5  or      edx, ecx
0x1800268a7  shl     edx, 2
0x1800268aa  or      edx, eax
0x1800268ac  lea     edi, ds:0[rdx*8]
0x1800268b3  test    r8d, r8d
0x1800268b6  jnz     short loc_1800268BD
0x1800268b8  mov     eax, r15d
0x1800268bb  jmp     short loc_1800268C7
0x1800268bd  xor     eax, eax
0x1800268bf  cmp     r8d, 2
0x1800268c3  cmovz   eax, r15d
0x1800268c7  or      edi, eax
0x1800268c9  mov     eax, [rbx]
0x1800268cb  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800268d0  mov     edx, eax
0x1800268d2  mov     [rbx], eax
0x1800268d4  jz      short loc_180026904
0x1800268d6  test    dl, 2
0x1800268d9  jnz     short loc_180026904
0x1800268db  mov     eax, edi
0x1800268dd  xor     eax, edx
0x1800268df  and     eax, 180h
0x1800268e4  xor     eax, edx
0x1800268e6  mov     ecx, eax
0x1800268e8  xor     ecx, edi
0x1800268ea  and     ecx, r15d
0x1800268ed  xor     ecx, eax
0x1800268ef  or      ecx, 1
0x1800268f2  mov     eax, ecx
0x1800268f4  xor     eax, edi
0x1800268f6  and     eax, 800h
0x1800268fb  xor     eax, ecx
0x1800268fd  or      eax, 2
0x180026900  mov     [rbx], eax
0x180026902  jmp     short loc_180026906
0x180026904  mov     eax, edx
0x180026906  mov     r8d, edx
0x180026909  and     r8d, 4
0x18002690d  jnz     short loc_180026922
0x18002690f  mov     ecx, edi
0x180026911  xor     ecx, eax
0x180026913  and     ecx, 400h
0x180026919  xor     ecx, eax
0x18002691b  or      ecx, 4
0x18002691e  mov     [rbx], ecx
0x180026920  jmp     short loc_180026924
0x180026922  mov     ecx, eax
0x180026924  mov     eax, edx
0x180026926  lock cmpxchg [rsi], ecx
0x18002692a  jnz     short loc_1800268CB
0x18002692c  test    r8d, r8d
0x18002692f  jnz     short loc_180026941
0x180026931  mov     r8d, ebp
0x180026934  mov     edx, 3
0x180026939  mov     rcx, rsi
0x18002693c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180026941  test    byte ptr [rbx], 2
0x180026944  jnz     short loc_18002696A
0x180026946  mov     eax, [rbx]
0x180026948  xor     eax, edi
0x18002694a  and     eax, 180h
0x18002694f  xor     eax, [rbx]
0x180026951  mov     ecx, eax
0x180026953  xor     ecx, edi
0x180026955  and     ecx, r15d
0x180026958  xor     ecx, eax
0x18002695a  or      ecx, 1
0x18002695d  mov     eax, ecx
0x18002695f  xor     eax, edi
0x180026961  and     eax, 800h
0x180026966  xor     eax, ecx
0x180026968  mov     [rbx], eax
0x18002696a  mov     rbp, [rsp+38h+arg_10]
0x18002696f  mov     rax, rbx
0x180026972  mov     rbx, [rsp+38h+arg_8]
0x180026977  add     rsp, 20h
0x18002697b  pop     r15
0x18002697d  pop     rdi
0x18002697e  pop     rsi
0x18002697f  retn
```
