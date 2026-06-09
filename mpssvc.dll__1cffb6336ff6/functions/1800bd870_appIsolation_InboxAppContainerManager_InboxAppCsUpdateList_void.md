# appIsolation::InboxAppContainerManager::InboxAppCsUpdateList(void *)

- ea: `0x1800bd870`
- end: `0x1800bda31`
- name: `?InboxAppCsUpdateList@InboxAppContainerManager@appIsolation@@QEAAKPEAX@Z`
- size: `449`
- prototype: `unsigned int(appIsolation::InboxAppContainerManager *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b5be8`

## callees

- `0x18000af3c`
- `0x18006f520`
- `0x1800bd870`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800bd8f3`
- `ntdll!RtlLengthSid` at `0x1800bd8f3`
- `ntdll!RtlCopySid` at `0x1800bd979`
- `ntdll!RtlCopySid` at `0x1800bd979`
- `ntdll!RtlEqualSid` at `0x1800bd8bd`
- `ntdll!RtlEqualSid` at `0x1800bd8bd`
- `fwbase!FwHResultToWindowsError` at `0x1800bd9af`
- `fwbase!FwHResultToWindowsError` at `0x1800bd9af`
- `fwbase!FwArrayAppend` at `0x1800bd9a7`
- `fwbase!FwArrayAppend` at `0x1800bd9a7`
- `fwbase!FwAlloc` at `0x1800bd8fd`
- `fwbase!FwAlloc` at `0x1800bd8fd`
- `fwbase!FwFree` at `0x1800bd9f1`
- `fwbase!FwFree` at `0x1800bd9f1`

## pseudocode

```c
__int64 __fastcall appIsolation::InboxAppContainerManager::InboxAppCsUpdateList(
        appIsolation::InboxAppContainerManager *this,
        void *a2)
{
  unsigned int v2; // edi
  unsigned int v3; // ebx
  __int64 v4; // rbp
  __int32 v7; // ebp
  ULONG v8; // edi
  void *v9; // rax
  void *v10; // rbx
  __int64 v11; // rcx
  unsigned int v12; // edi
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned int v16; // eax
  unsigned int v17; // eax
  __int128 v18; // [rsp+20h] [rbp-68h] BYREF
  __int128 v19; // [rsp+30h] [rbp-58h] BYREF

  v2 = *((_DWORD *)this + 14);
  v3 = 0;
  v4 = *((_QWORD *)this + 6);
  if ( !v2 )
  {
LABEL_4:
    v7 = *((_DWORD *)this + 14);
    v19 = 0;
    DWORD2(v19) = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
    v18 = 0;
    v8 = RtlLengthSid(a2);
    v9 = (void *)FwAlloc(v8);
    v10 = v9;
    if ( v9 )
    {
      RtlCopySid(v8, v9, a2);
      *((_QWORD *)&v18 + 1) = *((_QWORD *)this + 6);
      *(_QWORD *)&v19 = v10;
      LODWORD(v18) = v7;
      v16 = FwArrayAppend(16, FwShallowCopySidAndAttributes, &v18, &v19);
      v17 = FwHResultToWindowsError(v16);
      v12 = v17;
      if ( !v17 )
      {
        v7 = v18;
        *((_QWORD *)this + 6) = *((_QWORD *)&v18 + 1);
        goto LABEL_19;
      }
      v11 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
LABEL_17:
        FwFree(v19);
LABEL_19:
        _InterlockedExchange((volatile __int32 *)this + 14, v7);
        return v12;
      }
      v13 = 12;
      v14 = v17;
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      v12 = 14;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_17;
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_f89b9f9d100e330640241b1b67db84b7_Traceguids, 14);
        v11 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v11 == &WPP_GLOBAL_Control || (*(_BYTE *)(v11 + 28) & 1) == 0 )
        goto LABEL_17;
      v13 = 11;
      v14 = 14;
    }
    WPP_SF_d(*(_QWORD *)(v11 + 16), v13, WPP_f89b9f9d100e330640241b1b67db84b7_Traceguids, v14);
    goto LABEL_17;
  }
  while ( RtlEqualSid(a2, *(PSID *)(v4 + 16LL * v3)) != 1 )
  {
    if ( ++v3 >= v2 )
      goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x1800bd870  mov     [rsp+arg_10], rbx
0x1800bd875  push    rbp
0x1800bd876  push    rsi
0x1800bd877  push    rdi
0x1800bd878  push    r14
0x1800bd87a  push    r15
0x1800bd87c  sub     rsp, 60h
0x1800bd880  movaps  [rsp+88h+var_38], xmm6
0x1800bd885  mov     rax, cs:__security_cookie
0x1800bd88c  xor     rax, rsp
0x1800bd88f  mov     [rsp+88h+var_48], rax
0x1800bd894  mov     edi, [rcx+38h]
0x1800bd897  xor     r15d, r15d
0x1800bd89a  xor     ebx, ebx
0x1800bd89c  nop
0x1800bd89d  mov     rbp, [rcx+30h]
0x1800bd8a1  mov     r14, rdx
0x1800bd8a4  mov     rsi, rcx
0x1800bd8a7  xorps   xmm6, xmm6
0x1800bd8aa  test    edi, edi
0x1800bd8ac  jz      short loc_1800BD8D1
0x1800bd8ae  xchg    ax, ax
0x1800bd8b0  mov     edx, ebx
0x1800bd8b2  mov     rcx, r14; Sid1
0x1800bd8b5  add     rdx, rdx
0x1800bd8b8  mov     rdx, [rbp+rdx*8+0]; Sid2
0x1800bd8bd  call    cs:__imp_RtlEqualSid
0x1800bd8c3  cmp     al, 1
0x1800bd8c5  jz      loc_1800BD969
0x1800bd8cb  inc     ebx
0x1800bd8cd  cmp     ebx, edi
0x1800bd8cf  jb      short loc_1800BD8B0
0x1800bd8d1  mov     ebp, [rsi+38h]
0x1800bd8d4  xorps   xmm1, xmm1
0x1800bd8d7  xorps   xmm0, xmm0
0x1800bd8da  psrldq  xmm6, 8
0x1800bd8df  movups  [rsp+88h+var_58], xmm1
0x1800bd8e4  mov     rcx, r14; Sid
0x1800bd8e7  nop
0x1800bd8e8  movd    dword ptr [rsp+88h+var_58+8], xmm6
0x1800bd8ee  movups  [rsp+88h+var_68], xmm0
0x1800bd8f3  call    cs:__imp_RtlLengthSid
0x1800bd8f9  mov     ecx, eax
0x1800bd8fb  mov     edi, eax
0x1800bd8fd  call    cs:__imp_FwAlloc
0x1800bd903  mov     rbx, rax
0x1800bd906  test    rax, rax
0x1800bd909  jnz     short loc_1800BD971
0x1800bd90b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd912  lea     rbx, WPP_GLOBAL_Control
0x1800bd919  mov     edi, 0Eh
0x1800bd91e  cmp     rcx, rbx
0x1800bd921  jz      loc_1800BD9EC
0x1800bd927  test    byte ptr [rcx+1Ch], 1
0x1800bd92b  jz      short loc_1800BD94C
0x1800bd92d  mov     rcx, [rcx+10h]
0x1800bd931  lea     r8, WPP_f89b9f9d100e330640241b1b67db84b7_Traceguids
0x1800bd938  mov     edx, 0Ah
0x1800bd93d  mov     r9d, edi
0x1800bd940  call    WPP_SF_d
0x1800bd945  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd94c  cmp     rcx, rbx
0x1800bd94f  jz      loc_1800BD9EC
0x1800bd955  test    byte ptr [rcx+1Ch], 1
0x1800bd959  jz      loc_1800BD9EC
0x1800bd95f  mov     edx, 0Bh
0x1800bd964  mov     r9d, edi
0x1800bd967  jmp     short loc_1800BD9DC
0x1800bd969  mov     eax, r15d
0x1800bd96c  jmp     loc_1800BDA0B
0x1800bd971  mov     r8, r14; SourceSid
0x1800bd974  mov     rdx, rbx; DestinationSid
0x1800bd977  mov     ecx, edi; DestinationSidLength
0x1800bd979  call    cs:__imp_RtlCopySid
0x1800bd97f  mov     rax, [rsi+30h]
0x1800bd983  lea     r9, [rsp+88h+var_58]
0x1800bd988  lea     r8, [rsp+88h+var_68]
0x1800bd98d  mov     qword ptr [rsp+88h+var_68+8], rax
0x1800bd992  lea     rdx, ?FwShallowCopySidAndAttributes@@YAJPEBXPEAX@Z; FwShallowCopySidAndAttributes(void const *,void *)
0x1800bd999  mov     qword ptr [rsp+88h+var_58], rbx
0x1800bd99e  mov     ecx, 10h
0x1800bd9a3  mov     dword ptr [rsp+88h+var_68], ebp
0x1800bd9a7  call    cs:__imp_FwArrayAppend
0x1800bd9ad  mov     ecx, eax
0x1800bd9af  call    cs:__imp_FwHResultToWindowsError
0x1800bd9b5  mov     edi, eax
0x1800bd9b7  test    eax, eax
0x1800bd9b9  jz      short loc_1800BD9F9
0x1800bd9bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bd9c2  lea     rbx, WPP_GLOBAL_Control
0x1800bd9c9  cmp     rcx, rbx
0x1800bd9cc  jz      short loc_1800BD9EC
0x1800bd9ce  test    byte ptr [rcx+1Ch], 1
0x1800bd9d2  jz      short loc_1800BD9EC
0x1800bd9d4  mov     edx, 0Ch
0x1800bd9d9  mov     r9d, eax
0x1800bd9dc  mov     rcx, [rcx+10h]
0x1800bd9e0  lea     r8, WPP_f89b9f9d100e330640241b1b67db84b7_Traceguids
0x1800bd9e7  call    WPP_SF_d
0x1800bd9ec  mov     rcx, qword ptr [rsp+88h+var_58]
0x1800bd9f1  call    cs:__imp_FwFree
0x1800bd9f7  jmp     short loc_1800BDA06
0x1800bd9f9  mov     rcx, qword ptr [rsp+88h+var_68+8]
0x1800bd9fe  mov     ebp, dword ptr [rsp+88h+var_68]
0x1800bda02  mov     [rsi+30h], rcx
0x1800bda06  xchg    ebp, [rsi+38h]
0x1800bda09  mov     eax, edi
0x1800bda0b  mov     rcx, [rsp+88h+var_48]
0x1800bda10  xor     rcx, rsp; StackCookie
0x1800bda13  call    __security_check_cookie
0x1800bda18  mov     rbx, [rsp+88h+arg_10]
0x1800bda20  movaps  xmm6, [rsp+88h+var_38]
0x1800bda25  add     rsp, 60h
0x1800bda29  pop     r15
0x1800bda2b  pop     r14
0x1800bda2d  pop     rdi
0x1800bda2e  pop     rsi
0x1800bda2f  pop     rbp
0x1800bda30  retn
```
