# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<uint,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x1000d600`
- end: `0x1000d7ad`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AAEXABV?$unique_any_t@V?$unique_storage@U?$resource_policy@PAU_RTL_SRWLOCK@@P6GXPAU1@@Z$1?ReleaseSRWLockExclusive@@YGX0@ZU?$integral_constant@I$00@wistd@@PAU1@PAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `429`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1000d4f0`
- `0x1003a010`
- `0x1003fbf0`

## callees

- `0x1000d310`
- `0x1000d600`
- `0x1000eb60`
- `0x1005e3b0`
- `0x1005f064`

## pseudocode

```c
int __thiscall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(_DWORD *this, int a2)
{
  _DWORD *v2; // edx
  char *v3; // ecx
  char *v4; // esi
  int result; // eax
  int v6; // ebx
  volatile signed __int32 *v7; // edi
  unsigned __int32 v8; // ecx
  unsigned int v9; // edx
  char *v10; // eax
  int v11; // eax
  int (__thiscall *v12)(_DWORD, _DWORD, int, _DWORD, _DWORD); // esi
  unsigned int v13; // [esp+0h] [ebp-5Ch]
  char *v15; // [esp+14h] [ebp-48h]
  int v16; // [esp+18h] [ebp-44h]
  _DWORD v17[2]; // [esp+1Ch] [ebp-40h] BYREF
  char v18; // [esp+24h] [ebp-38h] BYREF
  int v19; // [esp+58h] [ebp-4h]

  v2 = this;
  v3 = (char *)this[6];
  v4 = (char *)this[5];
  result = v3 - v4;
  v15 = v3;
  if ( (unsigned int)(v3 - v4) >= 8 )
  {
    if ( v4 != v3 )
    {
      do
      {
        v6 = *(_DWORD *)v4;
        v7 = (volatile signed __int32 *)*((_DWORD *)v4 + 1);
        v16 = *(_DWORD *)v4;
        v19 = 0;
        v8 = _InterlockedAnd(v7, 0xFFC0401E);
        v9 = (v8 >> 1) & 0xF;
        if ( v9 )
        {
          v6 = v16;
          v9 &= ~_InterlockedOr(v7 + 1, v9);
        }
        v10 = (char *)v17;
        if ( (v9 & 1) != 0 )
        {
          v17[0] = v6;
          v10 = &v18;
          v17[1] = 65538;
        }
        if ( (v9 & 2) != 0 )
        {
          *(_DWORD *)v10 = v6;
          v6 = v16;
          *((_DWORD *)v10 + 1) = 65542;
          v10 += 8;
        }
        if ( (v9 & 4) != 0 )
        {
          *(_DWORD *)v10 = v6;
          v6 = v16;
          *((_DWORD *)v10 + 1) = 65539;
          v10 += 8;
        }
        if ( v9 >= 8 )
        {
          *(_DWORD *)v10 = v6;
          *((_DWORD *)v10 + 1) = 65543;
          v10 += 8;
        }
        if ( ((v8 >> 5) & 0x1FF) != 0 )
        {
          *(_DWORD *)v10 = v6;
          *((_WORD *)v10 + 3) = (v8 >> 5) & 0x1FF;
          *((_WORD *)v10 + 2) = 4 * ((v8 >> 14) & 1);
          v10 += 8;
        }
        if ( ((v8 >> 15) & 0x7F) != 0 )
        {
          *(_DWORD *)v10 = v6;
          *((_WORD *)v10 + 3) = (v8 >> 15) & 0x7F;
          *((_WORD *)v10 + 2) = (4 * ((v8 >> 22) & 1)) | 1;
          v10 += 8;
        }
        v11 = (v10 - (char *)v17) >> 3;
        if ( v11 > 0 )
          wil::details::WilApi_RecordFeatureUsageReports(
            (wil::details *)v17,
            (struct __WIL_RTL_FEATURE_USAGE_DATA *)v11,
            v13);
        v4 += 8;
        v19 = -1;
      }
      while ( v4 != v15 );
      v2 = this;
    }
    v12 = (int (__thiscall *)(_DWORD, _DWORD, int, _DWORD, _DWORD))g_wil_details_internalRecordFeatureUsage;
    result = v2[5];
    v2[6] = result;
    if ( v12 )
      return v12(v12, 0, 254, 0, 0);
    v12 = (int (__thiscall *)(_DWORD, _DWORD, int, _DWORD, _DWORD))g_wil_details_apiRecordFeatureUsage;
    if ( g_wil_details_apiRecordFeatureUsage )
      return v12(v12, 0, 254, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1000d600  mov     edi, edi
0x1000d602  push    ebp
0x1000d603  mov     ebp, esp
0x1000d605  push    0FFFFFFFFh
0x1000d607  push    offset ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AAEXABV?$unique_any_t@V?$unique_storage@U?$resource_policy@PAU_RTL_SRWLOCK@@P6GXPAU1@@Z$1?ReleaseSRWLockExclusive@@YGX0@ZU?$integral_constant@I$00@wistd@@PAU1@PAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z_SEH
0x1000d60c  mov     eax, large fs:0
0x1000d612  push    eax
0x1000d613  sub     esp, 40h
0x1000d616  mov     eax, ___security_cookie
0x1000d61b  xor     eax, ebp
0x1000d61d  mov     [ebp+var_10], eax
0x1000d620  push    ebx
0x1000d621  push    esi
0x1000d622  push    edi
0x1000d623  push    eax; unsigned int
0x1000d624  lea     eax, [ebp+var_C]
0x1000d627  mov     large fs:0, eax
0x1000d62d  mov     edx, ecx
0x1000d62f  mov     [ebp+var_4C], edx
0x1000d632  mov     ecx, [edx+18h]
0x1000d635  mov     eax, ecx
0x1000d637  mov     esi, [edx+14h]
0x1000d63a  sub     eax, esi
0x1000d63c  mov     [ebp+var_48], ecx
0x1000d63f  cmp     eax, 8
0x1000d642  jb      loc_1000D78F
0x1000d648  cmp     esi, ecx
0x1000d64a  jz      loc_1000D760
0x1000d650  mov     edx, 0FFC0401Eh
0x1000d655  mov     ebx, [esi]
0x1000d657  mov     edi, [esi+4]
0x1000d65a  mov     [ebp+var_44], ebx
0x1000d65d  mov     [ebp+var_4], 0
0x1000d664  mov     eax, [edi]
0x1000d666  mov     ecx, eax
0x1000d668  and     ecx, edx
0x1000d66a  lock cmpxchg [edi], ecx
0x1000d66e  jnz     short loc_1000D666
0x1000d670  mov     ecx, eax
0x1000d672  mov     edx, ecx
0x1000d674  shr     edx, 1
0x1000d676  and     edx, 0Fh
0x1000d679  jz      short loc_1000D691
0x1000d67b  lea     ebx, [edi+4]
0x1000d67e  mov     eax, [ebx]
0x1000d680  mov     edi, eax
0x1000d682  or      edi, edx
0x1000d684  lock cmpxchg [ebx], edi
0x1000d688  jnz     short loc_1000D680
0x1000d68a  mov     ebx, [ebp+var_44]
0x1000d68d  not     eax
0x1000d68f  and     edx, eax
0x1000d691  lea     eax, [ebp+var_40]
0x1000d694  test    dl, 1
0x1000d697  jz      short loc_1000D6A6
0x1000d699  mov     [ebp+var_40], ebx
0x1000d69c  lea     eax, [ebp+var_38]
0x1000d69f  mov     [ebp+var_3C], 10002h
0x1000d6a6  test    dl, 2
0x1000d6a9  jz      short loc_1000D6BA
0x1000d6ab  mov     [eax], ebx
0x1000d6ad  mov     ebx, [ebp+var_44]
0x1000d6b0  mov     dword ptr [eax+4], 10006h
0x1000d6b7  add     eax, 8
0x1000d6ba  test    dl, 4
0x1000d6bd  jz      short loc_1000D6CE
0x1000d6bf  mov     [eax], ebx
0x1000d6c1  mov     ebx, [ebp+var_44]
0x1000d6c4  mov     dword ptr [eax+4], 10003h
0x1000d6cb  add     eax, 8
0x1000d6ce  cmp     edx, 8
0x1000d6d1  jb      short loc_1000D6DF
0x1000d6d3  mov     [eax], ebx
0x1000d6d5  mov     dword ptr [eax+4], 10007h
0x1000d6dc  add     eax, 8
0x1000d6df  mov     edi, ecx
0x1000d6e1  shr     edi, 5
0x1000d6e4  test    edi, 1FFh
0x1000d6ea  jz      short loc_1000D70A
0x1000d6ec  mov     edx, ecx
0x1000d6ee  mov     [eax], ebx
0x1000d6f0  shr     edx, 0Eh
0x1000d6f3  and     edi, 1FFh
0x1000d6f9  and     edx, 1
0x1000d6fc  mov     [eax+6], di
0x1000d700  shl     edx, 2
0x1000d703  mov     [eax+4], dx
0x1000d707  add     eax, 8
0x1000d70a  mov     edx, ecx
0x1000d70c  shr     edx, 0Fh
0x1000d70f  test    dl, 7Fh
0x1000d712  jz      short loc_1000D730
0x1000d714  shr     ecx, 16h
0x1000d717  and     edx, 7Fh
0x1000d71a  and     ecx, 1
0x1000d71d  mov     [eax], ebx
0x1000d71f  shl     ecx, 2
0x1000d722  or      ecx, 1
0x1000d725  mov     [eax+6], dx
0x1000d729  mov     [eax+4], cx
0x1000d72d  add     eax, 8
0x1000d730  lea     ecx, [ebp+var_40]
0x1000d733  sub     eax, ecx
0x1000d735  sar     eax, 3
0x1000d738  test    eax, eax
0x1000d73a  jle     short loc_1000D745
0x1000d73c  push    eax; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1000d73d  mov     eax, ecx
0x1000d73f  push    eax; this
0x1000d740  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YGXPAU__WIL_RTL_FEATURE_USAGE_DATA@@I@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,uint)
0x1000d745  add     esi, 8
0x1000d748  mov     [ebp+var_4], 0FFFFFFFFh
0x1000d74f  mov     edx, 0FFC0401Eh
0x1000d754  cmp     esi, [ebp+var_48]
0x1000d757  jnz     loc_1000D655
0x1000d75d  mov     edx, [ebp+var_4C]
0x1000d760  mov     esi, _g_wil_details_internalRecordFeatureUsage
0x1000d766  mov     eax, [edx+14h]
0x1000d769  mov     [edx+18h], eax
0x1000d76c  test    esi, esi
0x1000d76e  jnz     short loc_1000D77A
0x1000d770  mov     esi, _g_wil_details_apiRecordFeatureUsage
0x1000d776  test    esi, esi
0x1000d778  jz      short loc_1000D78F
0x1000d77a  push    0
0x1000d77c  push    0
0x1000d77e  push    0FEh; unsigned int
0x1000d783  push    0; void *
0x1000d785  mov     ecx, esi
0x1000d787  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000d78d  call    esi ; _g_wil_details_internalRecordFeatureUsage
0x1000d78f  mov     ecx, [ebp+var_C]
0x1000d792  mov     large fs:0, ecx
0x1000d799  pop     ecx
0x1000d79a  pop     edi
0x1000d79b  pop     esi
0x1000d79c  pop     ebx
0x1000d79d  mov     ecx, [ebp+var_10]
0x1000d7a0  xor     ecx, ebp; StackCookie
0x1000d7a2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000d7a7  mov     esp, ebp
0x1000d7a9  pop     ebp
0x1000d7aa  retn    4
0x1005f070  jmp     ds:__imp____std_terminate
0x1005f890  nop
0x1005f891  nop
0x1005f892  mov     edx, [esp-4+arg_4]
0x1005f896  lea     eax, [edx+0Ch]
0x1005f899  mov     ecx, [edx-50h]
0x1005f89c  xor     ecx, eax; StackCookie
0x1005f89e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f8a3  mov     ecx, [edx-4]
0x1005f8a6  xor     ecx, eax; StackCookie
0x1005f8a8  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f8ad  mov     eax, offset stru_10062AD4
0x1005f8b2  jmp     ___CxxFrameHandler3
```
