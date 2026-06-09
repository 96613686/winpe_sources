# EapHost::ECPManager::ThreadFunc(void *)

- ea: `0x180010520`
- end: `0x180010646`
- name: `?ThreadFunc@ECPManager@EapHost@@CAIPEAX@Z`
- size: `294`
- prototype: `__int64 __fastcall(EapHost::ECPManager *this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001f60`
- `0x18000bbd8`
- `0x18000c150`
- `0x18000c40c`
- `0x18000f184`
- `0x180010520`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180010564`
- `ntdll!EtwEventEnabled` at `0x180010564`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001061d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001061d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180010546`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180010546`

## pseudocode

```c
__int64 __fastcall EapHost::ECPManager::ThreadFunc(EapHost::ECPManager *this)
{
  HRESULT v2; // ebx
  int v3; // r8d
  int v4; // r9d
  __int64 v5; // rax
  unsigned int v7; // ebx
  _BYTE v8[16]; // [rsp+30h] [rbp-838h] BYREF
  char *v9; // [rsp+40h] [rbp-828h]
  int v10; // [rsp+48h] [rbp-820h]
  int v11; // [rsp+4Ch] [rbp-81Ch]
  char v12[2048]; // [rsp+50h] [rbp-818h] BYREF

  v2 = CoInitializeEx(0, 0);
  if ( v2 >= 0 )
  {
    v7 = EapHost::ECPManager::Run(this);
    CoUninitialize();
    return v7;
  }
  else
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v12, 0x800u, " CoInitializeEx() failed, hr = 0x%x", v2) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      v5 = -1;
      do
        ++v5;
      while ( v12[v5] );
      v11 = 0;
      v10 = v5 + 1;
      v9 = v12;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugErrorEvent,
        v3,
        v4,
        (__int64)v8);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids,
        (unsigned int)v2);
    return 1;
  }
}

```

## disassembly

```asm
0x180010520  mov     [rsp+arg_8], rbx
0x180010525  push    rdi
0x180010526  sub     rsp, 860h
0x18001052d  mov     rax, cs:__security_cookie
0x180010534  xor     rax, rsp
0x180010537  mov     [rsp+868h+var_18], rax
0x18001053f  mov     rdi, rcx
0x180010542  xor     edx, edx; dwCoInit
0x180010544  xor     ecx, ecx; pvReserved
0x180010546  call    cs:__imp_CoInitializeEx
0x18001054c  mov     ebx, eax
0x18001054e  test    eax, eax
0x180010550  jns     loc_180010613
0x180010556  mov     rcx, cs:eaphost_Context
0x18001055d  lea     rdx, DebugErrorEvent
0x180010564  call    cs:__imp_EtwEventEnabled
0x18001056a  test    al, al
0x18001056c  jz      short loc_1800105DB
0x18001056e  mov     r9d, ebx
0x180010571  lea     r8, aCoinitializeex_0; " CoInitializeEx() failed, hr = 0x%x"
0x180010578  mov     edx, 800h; unsigned __int64
0x18001057d  lea     rcx, [rsp+868h+var_818]; char *
0x180010582  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180010587  test    eax, eax
0x180010589  js      short loc_1800105DB
0x18001058b  test    cs:byte_180020AC1, 8
0x180010592  jz      short loc_1800105DB
0x180010594  lea     rcx, [rsp+868h+var_818]
0x180010599  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001059d  inc     rax
0x1800105a0  cmp     byte ptr [rcx+rax], 0
0x1800105a4  jnz     short loc_18001059D
0x1800105a6  inc     eax
0x1800105a8  mov     [rsp+868h+var_81C], 0
0x1800105b0  lea     rcx, [rsp+868h+var_818]
0x1800105b5  mov     [rsp+868h+var_820], eax
0x1800105b9  lea     rax, [rsp+868h+var_838]
0x1800105be  mov     [rsp+868h+var_828], rcx
0x1800105c3  lea     rdx, DebugErrorEvent
0x1800105ca  mov     [rsp+868h+var_848], rax
0x1800105cf  lea     rcx, eaphost_Context
0x1800105d6  call    McGenEventWrite_EtwEventWriteTransfer
0x1800105db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800105e2  lea     rdx, WPP_GLOBAL_Control
0x1800105e9  cmp     rcx, rdx
0x1800105ec  jz      short loc_18001060C
0x1800105ee  test    byte ptr [rcx+1Ch], 1
0x1800105f2  jz      short loc_18001060C
0x1800105f4  mov     rcx, [rcx+10h]
0x1800105f8  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x1800105ff  mov     edx, 10h
0x180010604  mov     r9d, ebx
0x180010607  call    WPP_SF_d
0x18001060c  mov     eax, 1
0x180010611  jmp     short loc_180010625
0x180010613  mov     rcx, rdi; this
0x180010616  call    ?Run@ECPManager@EapHost@@AEAAIXZ; EapHost::ECPManager::Run(void)
0x18001061b  mov     ebx, eax
0x18001061d  call    cs:__imp_CoUninitialize
0x180010623  mov     eax, ebx
0x180010625  mov     rcx, [rsp+868h+var_18]
0x18001062d  xor     rcx, rsp; StackCookie
0x180010630  call    __security_check_cookie
0x180010635  mov     rbx, [rsp+868h+arg_8]
0x18001063d  add     rsp, 860h
0x180010644  pop     rdi
0x180010645  retn
```
