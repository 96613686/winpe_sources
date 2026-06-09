# CAsyncApi_SvcApiTask::Execute(void)

- ea: `0x180040190`
- end: `0x1800402f3`
- name: `?Execute@CAsyncApi_SvcApiTask@@MEAAXXZ`
- size: `355`
- prototype: `void __fastcall(CAsyncApi_SvcApiTask *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180036394`
- `0x18003c460`
- `0x180040190`
- `0x180080cac`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800402be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800402be`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800401a6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800401a6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800402a4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800402a4`

## pseudocode

```c
void __fastcall CAsyncApi_SvcApiTask::Execute(CAsyncApi_SvcApiTask *this)
{
  unsigned int v2; // ecx
  int v3; // eax
  unsigned int v4; // esi
  CObjectMonitor *v5; // rcx
  DWORD LastError; // eax
  void *v7; // [rsp+30h] [rbp+8h] BYREF

  if ( ImpersonateLoggedOnUser(*((HANDLE *)this + 13)) )
  {
    v2 = *((_DWORD *)this + 28);
    v7 = 0;
    if ( !v2 )
    {
      v5 = WPP_GLOBAL_Control;
      goto LABEL_14;
    }
    v3 = CscCom_UnMarshalFromGIT(v2, &GUID_f1ffcfc0_73e1_441b_a0c5_ba94d43e1acc, &v7);
    v4 = v3;
    if ( v3 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_8:
        if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147467262 )
        {
          if ( v5 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 2) != 0 )
            WPP_SF_d(*((_QWORD *)v5 + 2), 12, WPP_9dad3467f1b5334aaedce76d5a7ecec1_Traceguids, v4);
LABEL_18:
          if ( v7 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
          RevertToSelf();
          return;
        }
LABEL_14:
        if ( v5 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x800) != 0 )
          WPP_SF_(*((_QWORD *)v5 + 2), 13, WPP_9dad3467f1b5334aaedce76d5a7ecec1_Traceguids);
        (*(void (__fastcall **)(CAsyncApi_SvcApiTask *, void *))(*(_QWORD *)this + 64LL))(this, v7);
        goto LABEL_18;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_9dad3467f1b5334aaedce76d5a7ecec1_Traceguids,
        (unsigned int)v3);
    }
    v5 = WPP_GLOBAL_Control;
    goto LABEL_8;
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_9dad3467f1b5334aaedce76d5a7ecec1_Traceguids, LastError);
  }
}

```

## disassembly

```asm
0x180040190  mov     [rsp+arg_8], rbx
0x180040195  mov     [rsp+arg_10], rsi
0x18004019a  push    rdi
0x18004019b  sub     rsp, 20h
0x18004019f  mov     rdi, rcx
0x1800401a2  mov     rcx, [rcx+68h]; hToken
0x1800401a6  call    cs:__imp_ImpersonateLoggedOnUser
0x1800401ac  lea     rbx, WPP_GLOBAL_Control
0x1800401b3  test    eax, eax
0x1800401b5  jz      loc_1800402AC
0x1800401bb  mov     ecx, [rdi+70h]; unsigned int
0x1800401be  mov     [rsp+28h+arg_0], 0
0x1800401c7  test    ecx, ecx
0x1800401c9  jz      loc_180040250
0x1800401cf  lea     r8, [rsp+28h+arg_0]; void **
0x1800401d4  lea     rdx, _GUID_f1ffcfc0_73e1_441b_a0c5_ba94d43e1acc; struct _GUID *
0x1800401db  call    ?CscCom_UnMarshalFromGIT@@YAJKAEBU_GUID@@PEAPEAX@Z; CscCom_UnMarshalFromGIT(ulong,_GUID const &,void * *)
0x1800401e0  mov     esi, eax
0x1800401e2  test    eax, eax
0x1800401e4  jns     short loc_180040210
0x1800401e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800401ed  cmp     rcx, rbx
0x1800401f0  jz      short loc_180040217
0x1800401f2  test    byte ptr [rcx+1Ch], 2
0x1800401f6  jz      short loc_180040217
0x1800401f8  mov     rcx, [rcx+10h]
0x1800401fc  lea     r8, WPP_9dad3467f1b5334aaedce76d5a7ecec1_Traceguids
0x180040203  mov     edx, 0Fh
0x180040208  mov     r9d, eax
0x18004020b  call    WPP_SF_d
0x180040210  mov     rcx, cs:WPP_GLOBAL_Control
0x180040217  mov     edx, 80000000h
0x18004021c  lea     eax, [rsi+rdx]
0x18004021f  test    edx, eax
0x180040221  jnz     short loc_180040257
0x180040223  cmp     esi, 80004002h
0x180040229  jz      short loc_180040257
0x18004022b  cmp     rcx, rbx
0x18004022e  jz      short loc_18004028E
0x180040230  test    byte ptr [rcx+1Ch], 2
0x180040234  jz      short loc_18004028E
0x180040236  mov     rcx, [rcx+10h]
0x18004023a  lea     r8, WPP_9dad3467f1b5334aaedce76d5a7ecec1_Traceguids
0x180040241  mov     edx, 0Ch
0x180040246  mov     r9d, esi
0x180040249  call    WPP_SF_d
0x18004024e  jmp     short loc_18004028E
0x180040250  mov     rcx, cs:WPP_GLOBAL_Control
0x180040257  cmp     rcx, rbx
0x18004025a  jz      short loc_18004027A
0x18004025c  test    dword ptr [rcx+1Ch], 800h
0x180040263  jz      short loc_18004027A
0x180040265  mov     rcx, [rcx+10h]
0x180040269  lea     r8, WPP_9dad3467f1b5334aaedce76d5a7ecec1_Traceguids
0x180040270  mov     edx, 0Dh
0x180040275  call    WPP_SF_
0x18004027a  mov     rax, [rdi]
0x18004027d  mov     rcx, rdi
0x180040280  mov     rdx, [rsp+28h+arg_0]
0x180040285  mov     rax, [rax+40h]
0x180040289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004028e  mov     rcx, [rsp+28h+arg_0]
0x180040293  test    rcx, rcx
0x180040296  jz      short loc_1800402A4
0x180040298  mov     rax, [rcx]
0x18004029b  mov     rax, [rax+10h]
0x18004029f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402a4  call    cs:__imp_RevertToSelf
0x1800402aa  jmp     short loc_1800402E3
0x1800402ac  mov     rax, cs:WPP_GLOBAL_Control
0x1800402b3  cmp     rax, rbx
0x1800402b6  jz      short loc_1800402E3
0x1800402b8  test    byte ptr [rax+1Ch], 2
0x1800402bc  jz      short loc_1800402E3
0x1800402be  call    cs:__imp_GetLastError
0x1800402c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800402cb  lea     r8, WPP_9dad3467f1b5334aaedce76d5a7ecec1_Traceguids
0x1800402d2  mov     edx, 0Eh
0x1800402d7  mov     r9d, eax
0x1800402da  mov     rcx, [rcx+10h]
0x1800402de  call    WPP_SF_d
0x1800402e3  mov     rbx, [rsp+28h+arg_8]
0x1800402e8  mov     rsi, [rsp+28h+arg_10]
0x1800402ed  add     rsp, 20h
0x1800402f1  pop     rdi
0x1800402f2  retn
```
