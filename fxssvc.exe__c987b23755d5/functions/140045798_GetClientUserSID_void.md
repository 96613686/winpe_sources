# GetClientUserSID(void)

- ea: `0x140045798`
- end: `0x1400458c7`
- name: `?GetClientUserSID@@YAPEAXXZ`
- size: `303`
- prototype: `void *(void)`
- caller_count: `16`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000f2f0`
- `0x1400111e0`
- `0x14001186c`
- `0x1400120b8`
- `0x14001287c`
- `0x140012e20`
- `0x140015d90`
- `0x140016a60`
- `0x1400175c0`
- `0x140019980`
- `0x14001a290`
- `0x14001a6a0`
- `0x14001cf70`
- `0x14001f0a0`
- `0x140020f80`
- `0x140021530`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140045798`
- `0x140065dbc`
- `0x140073418`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140045835`
- `KERNEL32!GetLastError` at `0x140045835`
- `KERNEL32!SetLastError` at `0x14004581b`
- `KERNEL32!SetLastError` at `0x14004581b`
- `RPCRT4!RpcRevertToSelf` at `0x140045869`
- `RPCRT4!RpcRevertToSelf` at `0x140045869`
- `RPCRT4!RpcImpersonateClient` at `0x1400457dd`
- `RPCRT4!RpcImpersonateClient` at `0x1400457dd`

## pseudocode

```c
void *GetClientUserSID(void)
{
  unsigned int v0; // eax
  DWORD v1; // ebx
  DWORD v2; // ecx
  void *CurrentThreadSID; // rbx
  DWORD LastError; // eax
  unsigned int v6; // eax
  DWORD v7; // edi

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids);
  }
  v0 = RpcImpersonateClient(0);
  v1 = v0;
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v0);
    }
    v2 = v1;
LABEL_11:
    SetLastError(v2);
    return 0;
  }
  CurrentThreadSID = GetCurrentThreadSID();
  if ( !CurrentThreadSID )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, LastError);
    }
  }
  v6 = RpcRevertToSelf();
  v7 = v6;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids, v6);
    }
    pMemFree(CurrentThreadSID);
    v2 = v7;
    goto LABEL_11;
  }
  return CurrentThreadSID;
}

```

## disassembly

```asm
0x140045798  mov     [rsp+arg_0], rbx
0x14004579d  mov     [rsp+arg_8], rbp
0x1400457a2  push    rdi
0x1400457a3  sub     rsp, 20h
0x1400457a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400457ae  lea     rbp, WPP_GLOBAL_Control
0x1400457b5  cmp     rcx, rbp
0x1400457b8  jz      short loc_1400457DB
0x1400457ba  test    byte ptr [rcx+1Ch], 4
0x1400457be  jz      short loc_1400457DB
0x1400457c0  cmp     byte ptr [rcx+19h], 5
0x1400457c4  jb      short loc_1400457DB
0x1400457c6  mov     rcx, [rcx+10h]
0x1400457ca  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x1400457d1  mov     edx, 59h ; 'Y'
0x1400457d6  call    WPP_SF_
0x1400457db  xor     ecx, ecx; BindingHandle
0x1400457dd  call    cs:__imp_RpcImpersonateClient
0x1400457e3  mov     ebx, eax
0x1400457e5  test    eax, eax
0x1400457e7  jz      short loc_140045828
0x1400457e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400457f0  cmp     rcx, rbp
0x1400457f3  jz      short loc_140045819
0x1400457f5  test    byte ptr [rcx+1Ch], 4
0x1400457f9  jz      short loc_140045819
0x1400457fb  cmp     byte ptr [rcx+19h], 2
0x1400457ff  jb      short loc_140045819
0x140045801  mov     rcx, [rcx+10h]
0x140045805  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x14004580c  mov     edx, 5Ah ; 'Z'
0x140045811  mov     r9d, eax
0x140045814  call    WPP_SF_d
0x140045819  mov     ecx, ebx; dwErrCode
0x14004581b  call    cs:__imp_SetLastError
0x140045821  xor     eax, eax
0x140045823  jmp     loc_1400458B7
0x140045828  call    GetCurrentThreadSID
0x14004582d  mov     rbx, rax
0x140045830  test    rax, rax
0x140045833  jnz     short loc_140045869
0x140045835  call    cs:__imp_GetLastError
0x14004583b  mov     rcx, cs:WPP_GLOBAL_Control
0x140045842  cmp     rcx, rbp
0x140045845  jz      short loc_140045869
0x140045847  test    byte ptr [rcx+1Ch], 4
0x14004584b  jz      short loc_140045869
0x14004584d  cmp     byte ptr [rcx+19h], 2
0x140045851  jb      short loc_140045869
0x140045853  mov     rcx, [rcx+10h]
0x140045857  lea     edx, [rbx+5Bh]
0x14004585a  mov     r9d, eax
0x14004585d  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x140045864  call    WPP_SF_d
0x140045869  call    cs:__imp_RpcRevertToSelf
0x14004586f  mov     edi, eax
0x140045871  test    eax, eax
0x140045873  jz      short loc_1400458B4
0x140045875  mov     rcx, cs:WPP_GLOBAL_Control
0x14004587c  cmp     rcx, rbp
0x14004587f  jz      short loc_1400458A5
0x140045881  test    byte ptr [rcx+1Ch], 4
0x140045885  jz      short loc_1400458A5
0x140045887  cmp     byte ptr [rcx+19h], 2
0x14004588b  jb      short loc_1400458A5
0x14004588d  mov     rcx, [rcx+10h]
0x140045891  lea     r8, WPP_87ba4f79af383e9b772dd744c8d5323f_Traceguids
0x140045898  mov     edx, 5Ch ; '\'
0x14004589d  mov     r9d, eax
0x1400458a0  call    WPP_SF_d
0x1400458a5  mov     rcx, rbx; lpMem
0x1400458a8  call    pMemFree
0x1400458ad  mov     ecx, edi
0x1400458af  jmp     loc_14004581B
0x1400458b4  mov     rax, rbx
0x1400458b7  mov     rbx, [rsp+28h+arg_0]
0x1400458bc  mov     rbp, [rsp+28h+arg_8]
0x1400458c1  add     rsp, 20h
0x1400458c5  pop     rdi
0x1400458c6  retn
```
