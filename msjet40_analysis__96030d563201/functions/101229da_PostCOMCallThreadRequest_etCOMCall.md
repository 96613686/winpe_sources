# PostCOMCallThreadRequest(etCOMCall,...)

- ea: `0x101229da`
- end: `0x10122b4a`
- name: `?PostCOMCallThreadRequest@@YAJW4etCOMCall@@ZZ`
- size: `368`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x10017a30`
- `0x1003ecb0`
- `0x10040f30`
- `0x10121825`

## callees

- `0x10122815`
- `0x101229da`
- `0x10122f60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x10122a2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x10122a2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x101229f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x101229f2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x10122a35`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x10122a35`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x10122a7d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x10122a7d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10122a6f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x10122a6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10122ade`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10122ade`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10122a16`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10122a16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10122ac9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10122ac9`

## pseudocode

```c
int __cdecl PostCOMCallThreadRequest(int a1, char a2)
{
  HANDLE CurrentThread; // eax
  int *v3; // ecx
  int j; // edx
  int v5; // esi
  int *v6; // ebx
  int v7; // esi
  int *v8; // edi
  int *v10; // ecx
  int i; // edx
  int v12; // esi
  int *v13; // ebx
  int *v14; // edi
  _OWORD v15[18]; // [esp+Ch] [ebp-130h] BYREF

  if ( GetCurrentThreadId() == dword_10131078 || !dword_101310D8 )
  {
    v10 = (int *)&a2;
    for ( i = 0; ; ++i )
    {
      v12 = *v10++;
      v13 = v10;
      if ( v12 )
      {
        if ( v12 == 1 )
        {
          ++v10;
          *((_DWORD *)&v15[15] + i) = *v13;
        }
        else if ( v12 == 99 )
        {
          return COMCallProcess(v15);
        }
      }
      else
      {
        v10 += 4;
        v14 = (int *)&v15[i];
        *v14++ = *v13;
        *v14++ = v13[1];
        *v14 = v13[2];
        v14[1] = v13[3];
      }
    }
  }
  EnterCriticalSection(&CriticalSection);
  if ( dword_101310EC )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
      TokenHandle = 0;
  }
  v3 = (int *)&a2;
  dword_10130F48 = a1;
  for ( j = 0; ; ++j )
  {
    v5 = *v3++;
    v6 = v3;
    if ( v5 )
      break;
    v3 += 4;
    v8 = &dword_10130F88[4 * j];
    *v8++ = *v6;
    *v8++ = v6[1];
    *v8 = v6[2];
    v8[1] = v6[3];
LABEL_14:
    ;
  }
  if ( v5 == 1 )
  {
    ++v3;
    dword_10130F4C[j] = *v6;
    goto LABEL_14;
  }
  if ( v5 != 99 )
    goto LABEL_14;
  SetEvent(pHandles);
  if ( WaitForSingleObject(hHandle, 0xFFFFFFFF) )
  {
    v7 = -2147467259;
    dword_10130F2C = -2147467259;
  }
  else
  {
    v7 = dword_10130F2C;
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  LeaveCriticalSection(&CriticalSection);
  return v7;
}

```

## disassembly

```asm
0x101229da  mov     edi, edi
0x101229dc  push    ebp
0x101229dd  mov     ebp, esp
0x101229df  sub     esp, 130h
0x101229e5  mov     eax, ___security_cookie
0x101229ea  xor     eax, ebp
0x101229ec  mov     [ebp+var_4], eax
0x101229ef  push    ebx
0x101229f0  push    esi
0x101229f1  push    edi
0x101229f2  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x101229f8  cmp     eax, dword_10131078
0x101229fe  jz      loc_10122AE8
0x10122a04  cmp     dword_101310D8, 0
0x10122a0b  jz      loc_10122AE8
0x10122a11  push    offset CriticalSection; lpCriticalSection
0x10122a16  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10122a1c  cmp     dword_101310EC, 0
0x10122a23  jz      short loc_10122A44
0x10122a25  push    offset TokenHandle; TokenHandle
0x10122a2a  push    1; OpenAsSelf
0x10122a2c  push    4; DesiredAccess
0x10122a2e  call    ds:__imp__GetCurrentThread@0; GetCurrentThread()
0x10122a34  push    eax; ThreadHandle
0x10122a35  call    ds:__imp__OpenThreadToken@16; OpenThreadToken(x,x,x,x)
0x10122a3b  test    eax, eax
0x10122a3d  jnz     short loc_10122A44
0x10122a3f  mov     TokenHandle, eax
0x10122a44  mov     eax, [ebp+arg_0]
0x10122a47  lea     ecx, [ebp+arg_4]
0x10122a4a  mov     dword_10130F48, eax
0x10122a4f  xor     edx, edx
0x10122a51  mov     esi, [ecx]
0x10122a53  add     ecx, 4
0x10122a56  mov     eax, esi
0x10122a58  mov     ebx, ecx
0x10122a5a  sub     eax, 0
0x10122a5d  jz      short loc_10122AA2
0x10122a5f  sub     eax, 1
0x10122a62  jz      short loc_10122A94
0x10122a64  cmp     esi, 63h ; 'c'
0x10122a67  jnz     short loc_10122AB6
0x10122a69  push    pHandles; hEvent
0x10122a6f  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10122a75  push    0FFFFFFFFh; dwMilliseconds
0x10122a77  push    hHandle; hHandle
0x10122a7d  call    ds:__imp__WaitForSingleObject@8; WaitForSingleObject(x,x)
0x10122a83  test    eax, eax
0x10122a85  jz      short loc_10122AB9
0x10122a87  mov     esi, 80004005h
0x10122a8c  mov     dword_10130F2C, esi
0x10122a92  jmp     short loc_10122ABF
0x10122a94  mov     eax, [ebx]
0x10122a96  add     ecx, 4
0x10122a99  mov     dword_10130F4C[edx*4], eax
0x10122aa0  jmp     short loc_10122AB6
0x10122aa2  mov     edi, edx
0x10122aa4  add     ecx, 10h
0x10122aa7  shl     edi, 4
0x10122aaa  mov     esi, ebx
0x10122aac  add     edi, offset dword_10130F88
0x10122ab2  movsd
0x10122ab3  movsd
0x10122ab4  movsd
0x10122ab5  movsd
0x10122ab6  inc     edx
0x10122ab7  jmp     short loc_10122A51
0x10122ab9  mov     esi, dword_10130F2C
0x10122abf  mov     eax, TokenHandle
0x10122ac4  test    eax, eax
0x10122ac6  jz      short loc_10122AD9
0x10122ac8  push    eax; hObject
0x10122ac9  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10122acf  mov     TokenHandle, 0
0x10122ad9  push    offset CriticalSection; lpCriticalSection
0x10122ade  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10122ae4  mov     eax, esi
0x10122ae6  jmp     short loc_10122B17
0x10122ae8  lea     ecx, [ebp+arg_4]
0x10122aeb  xor     edx, edx
0x10122aed  mov     esi, [ecx]
0x10122aef  add     ecx, 4
0x10122af2  mov     eax, esi
0x10122af4  mov     ebx, ecx
0x10122af6  sub     eax, 0
0x10122af9  jz      short loc_10122B31
0x10122afb  sub     eax, 1
0x10122afe  jz      short loc_10122B26
0x10122b00  cmp     esi, 63h ; 'c'
0x10122b03  jnz     short loc_10122B47
0x10122b05  mov     ecx, [ebp+arg_0]
0x10122b08  lea     eax, [ebp+var_130]
0x10122b0e  push    eax
0x10122b0f  lea     edx, [ebp+var_40]
0x10122b12  call    ?COMCallProcess@@YGJW4etCOMCall@@QAKQAU_GUID@@@Z; COMCallProcess(etCOMCall,ulong * const,_GUID * const)
0x10122b17  mov     ecx, [ebp+var_4]
0x10122b1a  pop     edi
0x10122b1b  pop     esi
0x10122b1c  xor     ecx, ebp; StackCookie
0x10122b1e  pop     ebx
0x10122b1f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10122b24  leave
0x10122b25  retn
0x10122b26  mov     eax, [ebx]
0x10122b28  add     ecx, 4
0x10122b2b  mov     [ebp+edx*4+var_40], eax
0x10122b2f  jmp     short loc_10122B47
0x10122b31  mov     eax, edx
0x10122b33  lea     edi, [ebp+var_130]
0x10122b39  shl     eax, 4
0x10122b3c  add     ecx, 10h
0x10122b3f  add     edi, eax
0x10122b41  mov     esi, ebx
0x10122b43  movsd
0x10122b44  movsd
0x10122b45  movsd
0x10122b46  movsd
0x10122b47  inc     edx
0x10122b48  jmp     short loc_10122AED
```
