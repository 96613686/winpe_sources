# FREB_REQUEST_CONTEXT::MatchFailureDefinitionsStatusCode(IHttpContext *)

- ea: `0x180004604`
- end: `0x18000479d`
- name: `?MatchFailureDefinitionsStatusCode@FREB_REQUEST_CONTEXT@@QEAAXPEAVIHttpContext@@@Z`
- size: `409`
- prototype: `void __fastcall(FREB_REQUEST_CONTEXT *__hidden this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000209c`

## callees

- `0x180004604`
- `0x18000b010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800046d0`
- `iisutil!PuDbgPrint` at `0x1800046d0`

## string_xrefs

- `0x1800046a8`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_request_context.cxx`

## pseudocode

```c
void __fastcall FREB_REQUEST_CONTEXT::MatchFailureDefinitionsStatusCode(
        FREB_REQUEST_CONTEXT *this,
        struct IHttpContext *a2)
{
  __int64 v3; // rax
  __int64 v4; // r8
  unsigned int v5; // r11d
  __int64 v6; // r8
  __int64 v7; // r10
  int v8; // ecx
  int v9; // r9d
  unsigned __int16 v10; // ax
  bool v11; // zf
  unsigned __int16 v12; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int16 v13; // [rsp+78h] [rbp+10h] BYREF

  v12 = 0;
  v13 = 0;
  v3 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
  (*(void (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v3 + 184LL))(
    v3,
    &v12,
    &v13,
    0,
    0,
    0,
    0,
    0,
    0,
    0);
  if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_request_context.cxx",
      772,
      "FREB_REQUEST_CONTEXT::MatchFailureDefinitionsStatusCode",
      "Freb detected response status:%d, substatus:%d\n",
      v12,
      v13);
  v4 = *((_QWORD *)this + 10);
  v5 = *(_DWORD *)(v4 + 192);
  if ( v5 )
  {
    v6 = *(_QWORD *)(v4 + 184);
    v7 = 0;
    v8 = v12;
    v9 = v13;
    do
    {
      v10 = *(_WORD *)(v6 + 12 * v7 + 4);
      if ( *(_DWORD *)(v6 + 12 * v7) )
      {
        if ( v12 >= v10
          && (v12 != v10 || *(_WORD *)(v6 + 12 * v7 + 6) == 0xFFFF || v13 >= *(_WORD *)(v6 + 12 * v7 + 6))
          && v12 <= *(_WORD *)(v6 + 12 * v7 + 8)
          && (v12 != *(_WORD *)(v6 + 12 * v7 + 8)
           || *(_WORD *)(v6 + 12 * v7 + 10) == 0xFFFF
           || v13 <= *(_WORD *)(v6 + 12 * v7 + 10)) )
        {
LABEL_9:
          v11 = *((_DWORD *)this + 55) == 0;
          *((_DWORD *)this + 51) = 1;
          *((_DWORD *)this + 53) = 1;
          if ( v11 )
          {
            *((_DWORD *)this + 55) = v8;
            *((_DWORD *)this + 56) = v9;
          }
          return;
        }
      }
      else if ( v12 == v10 && (*(_WORD *)(v6 + 12 * v7 + 6) == 0xFFFF || v13 == *(_WORD *)(v6 + 12 * v7 + 6)) )
      {
        goto LABEL_9;
      }
      v7 = (unsigned int)(v7 + 1);
    }
    while ( (unsigned int)v7 < v5 );
  }
}

```

## disassembly

```asm
0x180004604  mov     [rsp+arg_10], rbx
0x180004609  push    rbp
0x18000460a  sub     rsp, 60h
0x18000460e  xor     eax, eax
0x180004610  mov     rbx, rcx
0x180004613  mov     [rsp+68h+arg_0], ax
0x180004618  mov     rcx, rdx
0x18000461b  mov     [rsp+68h+arg_8], ax
0x180004620  mov     rax, [rdx]
0x180004623  mov     rax, [rax+20h]
0x180004627  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000462c  mov     [rsp+68h+var_20], 0
0x180004635  lea     r8, [rsp+68h+arg_8]
0x18000463a  mov     [rsp+68h+var_28], 0
0x180004643  mov     rcx, rax
0x180004646  mov     [rsp+68h+var_30], 0
0x18000464f  xor     r9d, r9d
0x180004652  mov     rdx, [rax]
0x180004655  mov     [rsp+68h+var_38], 0
0x18000465e  mov     [rsp+68h+var_40], 0
0x180004667  mov     [rsp+68h+var_48], 0
0x180004670  mov     rax, [rdx+0B8h]
0x180004677  lea     rdx, [rsp+68h+arg_0]
0x18000467c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004681  mov     eax, cs:g_dwDebugFlags
0x180004687  test    al, 3
0x180004689  setnz   cl
0x18000468c  bt      eax, 1Fh
0x180004690  setb    al
0x180004693  test    al, cl
0x180004695  jz      short loc_1800046D6
0x180004697  movzx   eax, [rsp+68h+arg_8]
0x18000469c  lea     r9, aFrebRequestCon; "FREB_REQUEST_CONTEXT::MatchFailureDefin"...
0x1800046a3  movzx   ecx, [rsp+68h+arg_0]
0x1800046a8  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800046af  mov     dword ptr [rsp+68h+var_38], eax
0x1800046b3  mov     r8d, 304h
0x1800046b9  mov     dword ptr [rsp+68h+var_40], ecx
0x1800046bd  lea     rax, aFrebDetectedRe; "Freb detected response status:%d, subst"...
0x1800046c4  mov     rcx, cs:g_pDebug
0x1800046cb  mov     [rsp+68h+var_48], rax
0x1800046d0  call    cs:__imp_PuDbgPrint
0x1800046d6  mov     r8, [rbx+50h]
0x1800046da  mov     r11d, [r8+0C0h]
0x1800046e1  test    r11d, r11d
0x1800046e4  jz      short loc_180004750
0x1800046e6  mov     r8, [r8+0B8h]
0x1800046ed  xor     r10d, r10d
0x1800046f0  movzx   ecx, [rsp+68h+arg_0]
0x1800046f5  mov     ebp, 0FFFFh
0x1800046fa  movzx   r9d, [rsp+68h+arg_8]
0x180004700  lea     rdx, [r10+r10*2]
0x180004704  cmp     dword ptr [r8+rdx*4], 0
0x180004709  movzx   eax, word ptr [r8+rdx*4+4]
0x18000470f  jnz     short loc_18000475E
0x180004711  cmp     cx, ax
0x180004714  jnz     short loc_18000478F
0x180004716  cmp     bp, [r8+rdx*4+6]
0x18000471c  jz      short loc_180004726
0x18000471e  cmp     r9w, [r8+rdx*4+6]
0x180004724  jnz     short loc_18000478F
0x180004726  cmp     dword ptr [rbx+0DCh], 0
0x18000472d  mov     dword ptr [rbx+0CCh], 1
0x180004737  mov     dword ptr [rbx+0D4h], 1
0x180004741  jnz     short loc_180004750
0x180004743  mov     [rbx+0DCh], ecx
0x180004749  mov     [rbx+0E0h], r9d
0x180004750  mov     rbx, [rsp+68h+arg_10]
0x180004758  add     rsp, 60h
0x18000475c  pop     rbp
0x18000475d  retn
0x18000475e  cmp     cx, ax
0x180004761  jb      short loc_18000478F
0x180004763  jnz     short loc_180004775
0x180004765  cmp     [r8+rdx*4+6], bp
0x18000476b  jz      short loc_180004775
0x18000476d  cmp     r9w, [r8+rdx*4+6]
0x180004773  jb      short loc_18000478F
0x180004775  cmp     cx, [r8+rdx*4+8]
0x18000477b  ja      short loc_18000478F
0x18000477d  jnz     short loc_180004726
0x18000477f  cmp     [r8+rdx*4+0Ah], bp
0x180004785  jz      short loc_180004726
0x180004787  cmp     r9w, [r8+rdx*4+0Ah]
0x18000478d  jbe     short loc_180004726
0x18000478f  inc     r10d
0x180004792  cmp     r10d, r11d
0x180004795  jb      loc_180004700
0x18000479b  jmp     short loc_180004750
```
