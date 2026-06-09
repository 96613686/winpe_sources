# DeleteScope

- ea: `0x1800318b8`
- end: `0x180031aa4`
- name: `DeleteScope`
- size: `492`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034f44`
- `0x1800350e0`
- `0x180035b58`

## callees

- `0x18000ac60`
- `0x1800318b8`
- `0x180031aac`
- `0x180031b0c`
- `0x18003a1c4`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180031a35`
- `ntdll!RtlAcquireResourceExclusive` at `0x180031a35`
- `ntdll!RtlReleaseResource` at `0x180031a55`
- `ntdll!RtlReleaseResource` at `0x180031a55`
- `KERNEL32!HeapFree` at `0x1800319d2`
- `KERNEL32!HeapFree` at `0x1800319d2`

## string_xrefs

- `0x180031932`: `ENTERED DeleteScope: %d.%d.%d.%d/%d`
- `0x180031a64`: `LEFT DeleteScope`

## pseudocode

```c
__int64 __fastcall DeleteScope(__int64 *a1)
{
  char v2; // al
  __int64 v3; // rcx
  bool v4; // zf
  unsigned int i; // edi
  __int64 *v6; // r14
  __int64 *v7; // rax
  __int64 v8; // rsi
  __int64 **v9; // rcx
  __int64 *v10; // rcx
  __int64 **v11; // rax
  _QWORD *v12; // rdi
  _QWORD *j; // rbx
  int v15; // [rsp+20h] [rbp-868h]
  int v16; // [rsp+28h] [rbp-860h]
  int v17; // [rsp+30h] [rbp-858h]
  int v18; // [rsp+50h] [rbp-838h] BYREF
  _BYTE v19[2044]; // [rsp+54h] [rbp-834h] BYREF

  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v2 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v3 = *((unsigned int *)a1 + 5);
    LOWORD(v18) = 0;
    v17 = (unsigned __int8)MaskToMaskLen(v3);
    v16 = *((unsigned __int8 *)a1 + 19);
    v15 = *((unsigned __int8 *)a1 + 18);
    FormatRRASErrorString(
      &v18,
      L"ENTERED DeleteScope: %d.%d.%d.%d/%d",
      *((unsigned __int8 *)a1 + 16),
      *((unsigned __int8 *)a1 + 17),
      v15,
      v16,
      v17);
    v2 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v18);
      v2 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( *((_DWORD *)a1 + 4) )
  {
    if ( *((_DWORD *)a1 + 6) )
    {
      for ( i = 0; i < 0x39; ++i )
      {
        if ( !*((_DWORD *)a1 + 6) )
          break;
        v6 = &g_bbScopeTable[2 * i];
        v7 = (__int64 *)*v6;
        if ( (__int64 *)*v6 != v6 )
        {
          do
          {
            v8 = *v7;
            if ( (__int64 *)v7[2] == a1 )
            {
              if ( *(__int64 **)(v8 + 8) != v7 )
                goto LABEL_28;
              v9 = (__int64 **)v7[1];
              if ( *v9 != v7 )
                goto LABEL_28;
              *v9 = (__int64 *)v8;
              *(_QWORD *)(v8 + 8) = v9;
              --*((_DWORD *)a1 + 6);
              HeapFree(IPRouterHeap, 0, v7);
            }
            v7 = (__int64 *)v8;
          }
          while ( (__int64 *)v8 != v6 );
        }
      }
    }
    v10 = (__int64 *)*a1;
    if ( *(__int64 **)(*a1 + 8) != a1 || (v11 = (__int64 **)a1[1], *v11 != a1) )
LABEL_28:
      __fastfail(3u);
    *v11 = v10;
    v12 = a1 + 4;
    v10[1] = (__int64)v11;
    *((_DWORD *)a1 + 4) = 0;
    *((_DWORD *)a1 + 5) = -1;
    while ( (_QWORD *)*v12 != v12 )
    {
      DeleteScopeName(*v12);
      --*((_DWORD *)a1 + 7);
    }
    RtlAcquireResourceExclusive(&stru_18008C620, 1u);
    for ( j = a1 + 7; (_QWORD *)*j != j; DeleteZBR(*j) )
      ;
    RtlReleaseResource(&stru_18008C620);
    v4 = (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL;
  }
  else
  {
    v4 = v2 >= 0;
  }
  if ( !v4 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, L"LEFT DeleteScope");
  return 0;
}

```

## disassembly

```asm
0x1800318b8  push    rbx
0x1800318ba  push    rsi
0x1800318bb  push    rdi
0x1800318bc  push    r14
0x1800318be  sub     rsp, 868h
0x1800318c5  mov     rax, cs:__security_cookie
0x1800318cc  xor     rax, rsp
0x1800318cf  mov     [rsp+888h+var_38], rax
0x1800318d7  mov     rbx, rcx
0x1800318da  xor     eax, eax
0x1800318dc  lea     rcx, [rsp+888h+var_834]; void *
0x1800318e1  mov     [rsp+888h+var_838], eax
0x1800318e5  xor     edx, edx; Val
0x1800318e7  mov     r8d, 7FCh; Size
0x1800318ed  call    memset_0
0x1800318f2  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800318f9  test    al, al
0x1800318fb  jns     short loc_180031968
0x1800318fd  mov     ecx, [rbx+14h]
0x180031900  xor     eax, eax
0x180031902  mov     word ptr [rsp+888h+var_838], ax
0x180031907  call    MaskToMaskLen
0x18003190c  movzx   ecx, byte ptr [rbx+13h]
0x180031910  movzx   edx, byte ptr [rbx+12h]
0x180031914  movzx   r9d, byte ptr [rbx+11h]
0x180031919  movzx   r8d, byte ptr [rbx+10h]
0x18003191e  movzx   eax, al
0x180031921  mov     [rsp+888h+var_858], eax
0x180031925  mov     [rsp+888h+var_860], ecx
0x180031929  lea     rcx, [rsp+888h+var_838]
0x18003192e  mov     [rsp+888h+var_868], edx
0x180031932  lea     rdx, aEnteredDeletes_0; "ENTERED DeleteScope: %d.%d.%d.%d/%d"
0x180031939  call    FormatRRASErrorString
0x18003193e  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180031945  test    al, al
0x180031947  jns     short loc_180031968
0x180031949  lea     r8, [rsp+888h+var_838]
0x18003194e  lea     rdx, RasRtrmgrTraceInfo
0x180031955  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003195c  call    McTemplateU0z_EventWriteTransfer
0x180031961  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180031968  cmp     dword ptr [rbx+10h], 0
0x18003196c  jnz     short loc_180031975
0x18003196e  test    al, 80h
0x180031970  jmp     loc_180031A62
0x180031975  cmp     dword ptr [rbx+18h], 0
0x180031979  jbe     short loc_1800319E7
0x18003197b  xor     edi, edi
0x18003197d  cmp     dword ptr [rbx+18h], 0
0x180031981  jbe     short loc_1800319E7
0x180031983  mov     r14d, edi
0x180031986  lea     rcx, g_bbScopeTable
0x18003198d  shl     r14, 4
0x180031991  add     r14, rcx
0x180031994  mov     rax, [r14]
0x180031997  cmp     rax, r14
0x18003199a  jz      short loc_1800319E0
0x18003199c  mov     rsi, [rax]
0x18003199f  cmp     [rax+10h], rbx
0x1800319a3  jnz     short loc_1800319D8
0x1800319a5  cmp     [rsi+8], rax
0x1800319a9  jnz     loc_180031A9D
0x1800319af  mov     rcx, [rax+8]
0x1800319b3  cmp     [rcx], rax
0x1800319b6  jnz     loc_180031A9D
0x1800319bc  mov     [rcx], rsi
0x1800319bf  mov     r8, rax; lpMem
0x1800319c2  mov     [rsi+8], rcx
0x1800319c6  xor     edx, edx; dwFlags
0x1800319c8  dec     dword ptr [rbx+18h]
0x1800319cb  mov     rcx, cs:IPRouterHeap; hHeap
0x1800319d2  call    cs:__imp_HeapFree
0x1800319d8  mov     rax, rsi
0x1800319db  cmp     rsi, r14
0x1800319de  jnz     short loc_18003199C
0x1800319e0  inc     edi
0x1800319e2  cmp     edi, 39h ; '9'
0x1800319e5  jb      short loc_18003197D
0x1800319e7  mov     rcx, [rbx]
0x1800319ea  cmp     [rcx+8], rbx
0x1800319ee  jnz     loc_180031A9D
0x1800319f4  mov     rax, [rbx+8]
0x1800319f8  cmp     [rax], rbx
0x1800319fb  jnz     loc_180031A9D
0x180031a01  mov     [rax], rcx
0x180031a04  lea     rdi, [rbx+20h]
0x180031a08  mov     [rcx+8], rax
0x180031a0c  mov     dword ptr [rbx+10h], 0
0x180031a13  mov     dword ptr [rbx+14h], 0FFFFFFFFh
0x180031a1a  cmp     [rdi], rdi
0x180031a1d  jz      short loc_180031A2C
0x180031a1f  mov     rcx, [rdi]
0x180031a22  call    DeleteScopeName
0x180031a27  dec     dword ptr [rbx+1Ch]
0x180031a2a  jmp     short loc_180031A1A
0x180031a2c  mov     dl, 1; Wait
0x180031a2e  lea     rcx, stru_18008C620; Resource
0x180031a35  call    cs:__imp_RtlAcquireResourceExclusive
0x180031a3b  add     rbx, 38h ; '8'
0x180031a3f  cmp     [rbx], rbx
0x180031a42  jz      short loc_180031A4E
0x180031a44  mov     rcx, [rbx]
0x180031a47  call    DeleteZBR
0x180031a4c  jmp     short loc_180031A3F
0x180031a4e  lea     rcx, stru_18008C620; Resource
0x180031a55  call    cs:__imp_RtlReleaseResource
0x180031a5b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180031a62  jz      short loc_180031A7E
0x180031a64  lea     r8, aLeftDeletescop; "LEFT DeleteScope"
0x180031a6b  lea     rdx, RasRtrmgrTraceInfo
0x180031a72  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180031a79  call    McTemplateU0z_EventWriteTransfer
0x180031a7e  xor     eax, eax
0x180031a80  mov     rcx, [rsp+888h+var_38]
0x180031a88  xor     rcx, rsp; StackCookie
0x180031a8b  call    __security_check_cookie
0x180031a90  add     rsp, 868h
0x180031a97  pop     r14
0x180031a99  pop     rdi
0x180031a9a  pop     rsi
0x180031a9b  pop     rbx
0x180031a9c  retn
0x180031a9d  mov     ecx, 3
0x180031aa2  int     29h; Win8: RtlFailFast(ecx)
```
