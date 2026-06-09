# CUMRDPConnection::LogDisconnectDiagnosticsEvent(ulong,int,long,ulong)

- ea: `0x18004c178`
- end: `0x18004d584`
- name: `?LogDisconnectDiagnosticsEvent@CUMRDPConnection@@IEBAXKHJK@Z`
- size: `5132`
- prototype: `void __fastcall(CUMRDPConnection *__hidden this, unsigned int, int, int, unsigned int)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001ea20`
- `0x1800208b0`
- `0x1800544d4`

## callees

- `0x1800011dc`
- `0x18000f000`
- `0x18003394c`
- `0x180033958`
- `0x180033da0`
- `0x1800341a0`
- `0x180034970`
- `0x180034c4c`
- `0x18004833c`
- `0x18004c178`

## import_xrefs

- `RDPBASE!RDPServerStackDiagnostics_LogFailure` at `0x18004d39f`
- `RDPBASE!RDPServerStackDiagnostics_LogFailure` at `0x18004d39f`
- `RDPBASE!RDPServerStackDiagnostics_GetSymbolicNameFromCode` at `0x18004c2c7`
- `RDPBASE!RDPServerStackDiagnostics_GetSymbolicNameFromCode` at `0x18004d3bd`
- `RDPBASE!RDPServerStackDiagnostics_GetSymbolicNameFromCode` at `0x18004c2c7`
- `RDPBASE!RDPServerStackDiagnostics_GetSymbolicNameFromCode` at `0x18004d3bd`
- `RDPBASE!RDPServerStackDiagnostics_LogDisconnect` at `0x18004c2a9`
- `RDPBASE!RDPServerStackDiagnostics_LogDisconnect` at `0x18004c2a9`

## string_xrefs

- `0x18004c492`: `The session host lost connection to the service because of an unexpected network error. Check your network quality and configurations, then try again.`
- `0x18004c86d`: `The connection between the session host and the Azure Virtual Desktop service was unexpectedly disconnected.`
- `0x18004c400`: `The session host doesn't have Remote Desktop access or has a policy that blocks access.`
- `0x18004c3de`: `The user doesn't have access to the session host. The session host isn't configured to give this user Remote Desktop access privileges.`
- `0x18004c3cd`: `The server denied the connection because the session host configuration doesn't allow using saved credentials.`
- `0x18004cfab`: `User disconnected before completing logon. The connection was established but the user closed the client prior to reaching a logged on session.`
- `0x18004cc87`: `Token logon failed. Logon SubStatus code: 0x%x. Possible causes:\n\n1. The VM could not reach the Microsoft Entra ID authentication servers.\n\n2. Misconfigured multi-factor authentication enforcement.\nThe same restrictions should apply to both the client device and the Session Host VM.\nPer-user multifactor authentication should be disabled.\nFor more information see: https://learn.microsoft.com/en-us/azure/virtual-desktop/set-up-mfa \n\n3. The user is not assigned a role required to login to `
- `0x18004c987`: `Authentication failed. User account is not allowed to logon outside of logon hours.`
- `0x18004c8f2`: `Authentication failed. A specified logon session does not exist. It may already have been terminated.`
- `0x18004ca21`: `The service couldn't authenticate the user because the session host can't reach any Active Directory (AD) authentication servers.`
- `0x18004ca48`: `The authentication token is invalid.`
- `0x18004ca5e`: `The Local Security Authority cannot be contacted or another internal security error.`
- `0x18004cd2d`: `Unsupported security function: Potential mismatch between security policy settings on the client and host computers.`
- `0x18004caa3`: `The user is not granted network logon right on the session host. Make sure the user is authorized to access the session host from the network, then try again.`
- `0x18004c6de`: `Connection failed due to a brokering failure.`
- `0x18004c6cd`: `Connection failed due to invalid settings (brokering failure).`
- `0x18004c5b0`: `The session host licensing information is either invalid or missing. Reconfigure your session host license server and try again.`
- `0x18004c5eb`: `Access denied when trying to recreate the licensing store on the client as a non-admin user.`
- `0x18004c481`: `Connection failed, indirect display driver is not ready.`
- `0x18004c475`: `Connection failed, DWM process access failure.`
- `0x18004c4a4`: `Connection failed, Winlogon process access failure.`
- `0x18004c529`: `Connection failed, Csrss process access failure.`
- `0x18004c4e5`: `Connection failed, termservice is unable to process device PnP events or another major problem in termservice.`
- `0x18004c908`: `Connection failed due to a timeout waiting for the connection initiation sequence to complete. This may be because of pending credential prompt on the client.`
- `0x18004cae0`: `The session host disconnected from the service because of an unexpected network timeout. Check your network quality and make sure the session isn't using too many session host resources, then try again.`
- `0x18004caf1`: `The connection between the session host and the Azure Virtual Desktop service disconnected because of network data packet corruption. Make sure your network connection is reliable and try again.`
- `0x18004cd43`: `The connection between the session host and the Azure Virtual Desktop service was denied by the web proxy. Make sure that the web proxy configuration allows access to the AVD service.`
- `0x18004c84b`: `Disconnect due to virtual channel decompression error.`
- `0x18004cb4d`: `Connection failed (security error). Error code: 0x%x.`
- `0x18004cb80`: `Connection failed, can't create Input devices (Logon error). Error code: 0x%x.`
- `0x18004ce54`: `Connection failed, can't create Input devices due to input bus ERROR_DEVICE_NOT_AVAILABLE (Logon error). Error code: 0x%x.`
- `0x18004cb91`: `Connection failed, can't create internal graphics inter-process communication channel (Logon error). Error code: 0x%x.`
- `0x18004cba2`: `Connection failed, can't create graphics pipe subsystem (Logon error). Error code: 0x%x.`
- `0x18004cbc4`: `Connection failed during establishing a session (Logon error). Error code: 0x%x.`
- `0x18004cbe6`: `The session host lost connection to the client because of an unexpected network error in the Multipath transport. Check your network quality and configurations, then try again.`
- `0x18004cfde`: `The session host lost connection to the client because of a write thread hang. `
- `0x18004cfbc`: `The session host lost connection to the client because of a write to winsock failed. `
- `0x18004cfd2`: `The session host lost connection to the client because of a write post incomplete. `
- `0x18004d155`: `The session host lost connection to the client because of an unexpected network error in the Multipath websocket transport on the client side. Check your network quality and configurations, then try again.`
- `0x18004cc09`: `The session host lost connection to the client because of an unreliable network in the Multipath transport. Check your network quality and configurations, then try again.`
- `0x18004cda9`: `The session host lost connection to the client because of resources exhaustion in the Multipath transport. Check whether the host have enough assigned resources for the expected load.`
- `0x18004cdba`: `The session host lost connection to the client because of network data packet corruption in the Multipath transport. Make sure your network connection is reliable and try again.`
- `0x18004cdcb`: `The session host lost connection to the client because of an authentication failure in the Multipath transport.`
- `0x18004cbf8`: `Connection failed due to an error in the Multipath transport. Error code: 0x%x.`
- `0x18004cf25`: `Connection failed due to an error in the Multipath transport (SSPI). Error code: 0x%x.`
- `0x18004cde1`: `Connection failed due to an error in the Multipath Private transport. Error code: 0x%x.`
- `0x18004ce08`: `Disconnecting the session host Multipath transport did not receive acknowlegment from the peer. The client may have been already closed.`
- `0x18004ce1d`: `Disconnecting the session host Multipath transport appears to hang on its read thread such that packets received in the WinSock layer donot get to forwarded to the UDP transport layer`
- `0x18004d0d6`: `The session host lost connection to the client because of an internal error in the Multipath sockets transport stack.`
- `0x18004d0af`: `The session host lost connection to the client because of device not connected to the internet. Check your network quality and configurations, then try again.`
- `0x18004d099`: `The session host lost connection to the client because of an invalid request in the Multipath transport. Error code: 0x%x.`
- `0x18004d083`: `The session host lost connection to the client because of a timeout waiting for a response in the Multipath transport. Error code: 0x%x.`
- `0x18004d072`: `The session host lost connection to the client because of a request denied in the Multipath transport. Error code: 0x%x.`
- `0x18004d0fd`: `The session host lost connection to the client because of a transport shutdown in the Multipath transport. Error code: 0x%x.`
- `0x18004d192`: `The session host lost connection to the client because of a remote unreachable in the Multipath transport.`
- `0x18004d1a8`: `The session host lost connection to the client because of a connection cancelled in the Multipath transport. Error code: 0x%x.`
- `0x18004d17c`: `The session host lost connection to the client because of a remote reset in the Multipath transport. Error code: 0x%x.`
- `0x18004d0c0`: `Connection failed due to an invalid packet buffer size in the Multipath transport.`
- `0x18004d144`: `The session host could not connect to the client because of a generic websocket error in the Multipath transport.`
- `0x18004d2a1`: `The session host lost connection to the client because of an unexpected error in the Multipath websocket transport websocket response.`
- `0x18004d1be`: `The session host lost connection to the client because of a server error in the Multipath websocket transport. Error code: 0x%x.`
- `0x18004d286`: `The session host lost connection to the client because of an invalid request in the Multipath websocket transport. Error code: 0x%x.`
- `0x18004d270`: `The session host lost connection to the client because of a timeout waiting for a response in the Multipath websocket transport. Error code: 0x%x.`
- `0x18004d25f`: `The session host lost connection to the client because of a request denied in the Multipath websocket transport. Error code: 0x%x.`
- `0x18004d24e`: `The session host lost connection to the client because of a transport shutdown in the Multipath websocket transport. Error code: 0x%x.`
- `0x18004d2b7`: `The session host lost connection to the client because of a remote unreachable in the Multipath websocket transport.`
- `0x18004d303`: `The session host lost connection to the client because of a connection cancelled in the Multipath websocket transport. Error code: 0x%x.`
- `0x18004d345`: `The session host lost connection to the client because of a remote reset in the Multipath websocket transport. Error code: 0x%x.`
- `0x18004d319`: `The session host lost connection to the client because of a network data packet corruption in the Multipath websocket transport. Your network connection may be unreliable.`
- `0x18004d2f2`: `The session host Multipath websocket connection was denied by the web proxy. Make sure that the web proxy configuration allows access to the AVD service.`
- `0x18004d334`: `Connection failed due to an error in the Multipath websocket transport. Error code: 0x%x.`
- `0x18004c778`: `Connection failed, session broker error. See error info code for details`
- `0x18004c76c`: `An X.224 Data packet was received which did not contain a complete MCS.`
- `0x18004c74a`: `X224 layer failed to activate the Security Filter Driver.`
- `0x18004cf8b`: `RDP failed to encrypt protocol data.`
- `0x18004d23d`: `Connection failed, see protocol error code for details`

## pseudocode

```c
void __fastcall CUMRDPConnection::LogDisconnectDiagnosticsEvent(
        CUMRDPConnection *this,
        unsigned int a2,
        int a3,
        int a4,
        unsigned int a5)
{
  unsigned int v7; // ebx
  char *v9; // rsi
  unsigned int v10; // edi
  int v11; // r13d
  __int64 v12; // r8
  int v13; // eax
  __int64 v14; // rdx
  __int64 SymbolicNameFromCode; // rax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  const char *v19; // r9
  char *v20; // rax
  const char *v21; // rcx
  __int64 v22; // rdx
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm1
  void *v31; // rax
  unsigned int v32; // eax
  __int64 v33; // rax
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  unsigned int v37; // [rsp+80h] [rbp-80h] BYREF
  BOOL v38; // [rsp+84h] [rbp-7Ch] BYREF
  int v39; // [rsp+88h] [rbp-78h] BYREF
  CUMRDPConnection *v40; // [rsp+90h] [rbp-70h] BYREF
  const char *v41; // [rsp+98h] [rbp-68h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-60h] BYREF
  void *Block; // [rsp+A8h] [rbp-58h]
  char *v44; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v45; // [rsp+B8h] [rbp-48h] BYREF
  const char *v46; // [rsp+C0h] [rbp-40h] BYREF
  const char *v47; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v48; // [rsp+D0h] [rbp-30h] BYREF
  char Buffer[272]; // [rsp+E0h] [rbp-20h] BYREF
  char Format[928]; // [rsp+1F0h] [rbp+F0h] BYREF

  v40 = this;
  v38 = 0;
  v7 = 26;
  v37 = 2;
  v39 = 26;
  v9 = "Connection failed, see disconnect code for details";
  v10 = 777;
  memset_0(Buffer, 0, 0x104u);
  v11 = 0;
  Block = 0;
  if ( a2 > 0x100 )
  {
    if ( a2 <= 0x400 )
    {
      if ( a2 != 1024 )
      {
        if ( a2 > 0x106 )
        {
          switch ( a2 )
          {
            case 0x107u:
            case 0x108u:
              goto LABEL_84;
            case 0x109u:
              v10 = 702;
              v9 = "Can't upgrade license. The requested license has not been found.";
              v7 = 35;
              goto LABEL_14;
            case 0x10Au:
              v10 = 702;
              v9 = "Connection denied due to licensing. Server is in null mode. Licenses could be expired or there could "
                   "be not enough Per-CPU CALs.";
              v7 = 29;
              goto LABEL_14;
            case 0x10Bu:
              v10 = 702;
              v7 = 36;
              v9 = "Access denied when trying to recreate the licensing store on the client as a non-admin user.";
              goto LABEL_14;
          }
        }
        else
        {
          switch ( a2 )
          {
            case 0x106u:
              goto LABEL_84;
            case 0x101u:
              v10 = 702;
              v9 = "The session host licensing information is either invalid or missing. Reconfigure your session host li"
                   "cense server and try again.";
              v7 = 28;
              goto LABEL_14;
            case 0x102u:
              v10 = 702;
              v9 = "Connection failed because a license is not available.";
              v7 = 13;
              goto LABEL_14;
            case 0x103u:
LABEL_84:
              v10 = 702;
              v9 = "Connection failed due to a license processing failure.";
              v7 = 31;
              goto LABEL_14;
          }
          if ( a2 - 260 <= 1 )
          {
            v10 = 702;
            v9 = "Connection failed due to an invalid license.";
            v7 = 30;
            goto LABEL_14;
          }
        }
LABEL_296:
        v12 = v37;
        if ( a2 - 4096 > 0x6FFF )
        {
          v9 = "Connection failed, see error info code for details";
        }
        else
        {
          v7 = 27;
          v9 = "Connection failed, see protocol error code for details";
        }
        goto LABEL_15;
      }
LABEL_102:
      v7 = 23;
      v9 = "Connection failed due to a brokering failure.";
      goto LABEL_14;
    }
    if ( a2 <= 0x1163 )
    {
      if ( a2 == 4451 )
      {
        v7 = 69;
        v9 = "The session host lost connection to the client because of an unreliable network in the Multipath transport."
             " Check your network quality and configurations, then try again.";
        goto LABEL_14;
      }
      if ( a2 > 0x113F )
      {
        switch ( a2 )
        {
          case 0x1140u:
            v10 = 701;
            v9 = "Authentication failed. User account is not allowed to logon outside of logon hours.";
            v7 = 55;
            goto LABEL_14;
          case 0x1141u:
            v10 = 703;
            CUMRDPConnection::GetDiagnosticsCodeForAuthorizationFailure(
              v40,
              (enum RdpServerConnectionDiagnosticCode *)&v39);
            v7 = v39;
            v9 = "Unexpected user account connected. This user isn't authorized so sign in to the session host.";
            if ( v39 != 70 )
              v9 = "This user isn't authorized so sign in to the session host.";
            goto LABEL_14;
          case 0x1142u:
            v10 = 703;
            v9 = "Authorization failed. The user is not authorized for logon to this workstation.";
            v7 = 56;
            goto LABEL_14;
          case 0x1143u:
            v7 = 58;
            v9 = "The session host disconnected from the service because of an unexpected network timeout. Check your net"
                 "work quality and make sure the session isn't using too many session host resources, then try again.";
            goto LABEL_14;
          case 0x1144u:
            v7 = 27;
            v9 = "Disconnect due to invalid data received.";
            goto LABEL_14;
          case 0x1145u:
            v7 = 57;
            v9 = "The connection between the session host and the Azure Virtual Desktop service disconnected because of n"
                 "etwork data packet corruption. Make sure your network connection is reliable and try again.";
            goto LABEL_14;
          case 0x1146u:
            v19 = "Connection failed (transport error). Error code: 0x%x.";
            goto LABEL_148;
          case 0x1147u:
            v19 = "Connection failed (security error). Error code: 0x%x.";
            goto LABEL_148;
          case 0x1148u:
            v7 = 27;
            v9 = "Disconnect due to http internal error.";
            goto LABEL_14;
          case 0x1149u:
            v7 = 27;
            v9 = "Disconnect due to invalid http server response.";
            goto LABEL_14;
          case 0x114Au:
            v10 = 704;
            v19 = "Connection failed, can't create Input devices (Logon error). Error code: 0x%x.";
            goto LABEL_148;
          case 0x114Bu:
            v10 = 704;
            v19 = "Connection failed, timeout reached while waiting for graphics to initialize (Logon error). Error code: 0x%x.";
            goto LABEL_148;
          case 0x114Cu:
            v10 = 704;
            v19 = "Connection failed, can't create internal graphics inter-process communication channel (Logon error). E"
                  "rror code: 0x%x.";
            goto LABEL_148;
          case 0x114Du:
            v10 = 704;
            v19 = "Connection failed, can't create graphics pipe subsystem (Logon error). Error code: 0x%x.";
            goto LABEL_148;
          case 0x114Eu:
            v10 = 704;
            v19 = "Connection failed during establishing a session (Logon error). Error code: 0x%x.";
            goto LABEL_148;
          case 0x1151u:
            v7 = 61;
            v9 = "Connection failed due to client not supporting screen capture protection.";
            goto LABEL_14;
          case 0x1152u:
            v10 = 701;
            v9 = aTheClientCould;
            v7 = 47;
            goto LABEL_14;
          case 0x1153u:
            v10 = 701;
            v9 = "A different remote desktop client tried to connect to this session while the auto-reconnect setting was"
                 " disabled or the original session was logged off. To reconnect, end the current session and start a new one.";
            v7 = 48;
            goto LABEL_14;
          case 0x1154u:
            v10 = 701;
            v9 = aTheClientCould_0;
            v7 = 49;
            goto LABEL_14;
          case 0x1155u:
            v10 = 701;
            v9 = "Auto reconnect failed. Invalid cookie.";
            v7 = 50;
            goto LABEL_14;
          case 0x1156u:
            v10 = 701;
            v9 = "Auto reconnect failed. Failed to log on.";
            v7 = 27;
            goto LABEL_14;
          case 0x1157u:
            v10 = 701;
            v19 = "Authentication failed. See code for details. Error code: 0x%x.";
            v7 = 81;
            goto LABEL_149;
          case 0x1158u:
            v10 = 703;
            v9 = "The user is not granted network logon right on the session host. Make sure the user is authorized to ac"
                 "cess the session host from the network, then try again.";
            v7 = 91;
            goto LABEL_14;
          case 0x1159u:
            v10 = 701;
            v9 = "The service couldn't authenticate the user because the session host can't reach any Active Directory (A"
                 "D) authentication servers.";
            v7 = 59;
            goto LABEL_14;
          case 0x115Au:
            v10 = 701;
            v19 = "Logon operation failed, see code for details. Error code: 0x%x.";
            goto LABEL_148;
          case 0x115Bu:
            v7 = 27;
            v9 = "Disconnect due to a failure in decoding graphics message from the client.";
            goto LABEL_14;
          case 0x115Cu:
            goto LABEL_188;
          case 0x115Du:
            v10 = 701;
            v9 = "The authentication token is invalid.";
            v7 = 27;
            goto LABEL_14;
          case 0x115Eu:
            v10 = 701;
            v9 = "The Local Security Authority cannot be contacted or another internal security error.";
            v7 = 27;
            goto LABEL_14;
          case 0x115Fu:
            v7 = 27;
            v9 = "Disconnect due to invalid operation or handle state in the websocket transport.";
            goto LABEL_14;
          case 0x1160u:
            v38 = 1;
            v7 = 66;
            goto LABEL_14;
          case 0x1161u:
            v38 = 1;
            v7 = 67;
            goto LABEL_14;
          case 0x1162u:
            v7 = 68;
            v9 = "The session host lost connection to the client because of an unexpected network error in the Multipath "
                 "transport. Check your network quality and configurations, then try again.";
            goto LABEL_187;
          default:
            goto LABEL_296;
        }
      }
      if ( a2 == 4415 )
      {
        v10 = 701;
        v9 = "This user account is locked, so the user can't sign in.";
        v7 = 54;
        goto LABEL_14;
      }
      if ( a2 <= 0x10DE )
      {
        if ( a2 == 4318 )
        {
          v7 = 27;
          v9 = "Disconnect due to invalid input PDU lenght.";
          goto LABEL_14;
        }
        if ( a2 > 0x411 )
        {
          if ( a2 != 1042 )
          {
            switch ( a2 )
            {
              case 0x1009u:
                v7 = 27;
                v9 = "An X.224 Data packet was received which did not contain a complete MCS.";
                goto LABEL_14;
              case 0x100Bu:
                v7 = 27;
                v9 = "An X.224 packet was received with an unknown TPDU type.";
                goto LABEL_14;
              case 0x1020u:
              case 0x1021u:
                v7 = 27;
                v9 = "X224 layer failed to activate the Security Filter Driver.";
                goto LABEL_14;
              case 0x1022u:
                v10 = 701;
                v9 = "SSL required by server, no client authentication negotiation allowed.";
                v7 = 27;
                goto LABEL_14;
              case 0x10CAu:
                v7 = 27;
                v9 = "Disconnect due to unknown packet type received.";
                goto LABEL_14;
            }
            goto LABEL_296;
          }
        }
        else if ( a2 != 1041 )
        {
          if ( a2 == 1026 || a2 == 1028 )
            goto LABEL_102;
          if ( a2 != 1029 && a2 != 1030 && a2 != 1031 && a2 != 1032 && a2 != 1033 )
          {
            if ( a2 == 1040 )
            {
              v7 = 65;
              v9 = "Connection failed due to invalid settings (brokering failure).";
              goto LABEL_14;
            }
            goto LABEL_296;
          }
        }
        v9 = "Connection failed, session broker error. See error info code for details";
        goto LABEL_14;
      }
      if ( a2 <= 0x1137 )
      {
        switch ( a2 )
        {
          case 0x1137u:
            v7 = 46;
            v9 = "The connection between the session host and the Azure Virtual Desktop service was unexpectedly disconnected.";
            goto LABEL_14;
          case 0x10EAu:
            v7 = 27;
            v9 = "The client capabilities received were unacceptable.";
            goto LABEL_14;
          case 0x10ECu:
            v7 = 27;
            v9 = "Disconnect due to virtual channel decompression error.";
            goto LABEL_14;
          case 0x112Bu:
            v7 = 27;
            v9 = "Disconnect due to virtual channel data too long.";
            goto LABEL_14;
          case 0x112Du:
            v7 = 27;
            v9 = "Disconnect due to graphics mode not supported.";
            goto LABEL_14;
          case 0x112Fu:
            v7 = 27;
            v9 = "Disconnect due to a failure in graphics subsystem.";
            goto LABEL_14;
          case 0x1133u:
            v7 = 27;
            v9 = "The VC manager failed DVC data processing/decoding.";
            goto LABEL_14;
          case 0x1135u:
            v7 = 27;
            v9 = "Monitor geometry validation failed.";
            goto LABEL_14;
          case 0x1136u:
            v7 = 27;
            v9 = "Invalid monitor count.";
            goto LABEL_14;
        }
        goto LABEL_296;
      }
      if ( a2 == 4408 )
      {
        v19 = "Connection failed (network error). Error code: 0x%x.";
      }
      else
      {
        if ( a2 != 4409 )
        {
          switch ( a2 )
          {
            case 0x113Au:
              v7 = 60;
              v9 = "Connection failed due to a timeout waiting for the connection initiation sequence to complete. This m"
                   "ay be because of pending credential prompt on the client.";
              break;
            case 0x113Bu:
              v10 = 701;
              v9 = "Authentication failed. A specified logon session does not exist. It may already have been terminated.";
              v7 = 52;
              break;
            case 0x113Cu:
              v10 = 701;
              v9 = "The username or password is invalid. Reenter your credentials and try again.";
              v7 = 3;
              break;
            default:
              v10 = 701;
              if ( a2 == 4413 )
              {
                v9 = "The password you entered has expired. Change your password and try again.";
                v7 = 4;
              }
              else
              {
                v7 = 53;
                v9 = "Authentication failed. User account is disabled.";
              }
              break;
          }
          goto LABEL_14;
        }
        v19 = "Connection failed (RDP error). Error code: 0x%x.";
      }
      goto LABEL_148;
    }
    if ( a2 <= 0x11F5 )
    {
      if ( a2 == 4597 )
      {
        v7 = 99;
        v9 = "Connection failed due to client not supporting display protection.";
        goto LABEL_14;
      }
      if ( a2 <= 0x1175 )
      {
        if ( a2 != 4469 )
        {
          switch ( a2 )
          {
            case 0x1164u:
              v7 = 71;
              v9 = "Connection failed due to client not supporting watermarking.";
              goto LABEL_14;
            case 0x1165u:
              v7 = 27;
              v9 = "Disconnect due to a timeout getting graphics pipe acknowlegment message from the client.";
              goto LABEL_14;
            case 0x1166u:
              v7 = 72;
              v9 = "The connection between the session host and the Azure Virtual Desktop service was denied by the web p"
                   "roxy. Make sure that the web proxy configuration allows access to the AVD service.";
              goto LABEL_14;
            case 0x1167u:
              v7 = 73;
              v19 = "Connection failed due to an error handling connection in termsrv. Error code: 0x%x.";
              goto LABEL_149;
            case 0x1168u:
              v7 = 76;
              v9 = "The session host lost connection to the client because of resources exhaustion in the Multipath trans"
                   "port. Check whether the host have enough assigned resources for the expected load.";
              goto LABEL_14;
            case 0x1169u:
              v7 = 27;
              snprintf_s(
                Buffer,
                0x104u,
                0x103u,
                "Connection failed due to an error in the Multipath Private transport. Error code: 0x%x.",
                a4);
              v9 = Buffer;
              goto LABEL_187;
            case 0x116Au:
              v7 = 74;
              v9 = "The session host lost connection to the client because of network data packet corruption in the Multi"
                   "path transport. Make sure your network connection is reliable and try again.";
              goto LABEL_14;
            case 0x116Bu:
              v7 = 75;
              v9 = "The session host lost connection to the client because of an authentication failure in the Multipath transport.";
              goto LABEL_14;
            case 0x116Cu:
              v7 = 27;
              v9 = "Disconnect due to a failure in graphics subsystem initialization.";
              goto LABEL_14;
            case 0x116Du:
              v7 = 27;
              v9 = "Disconnect due to a failure in graphics pipeline restart.";
              goto LABEL_14;
            case 0x116Eu:
              v10 = 701;
              v9 = "Unsupported security function: Potential mismatch between security policy settings on the client and host computers.";
              v7 = 78;
              goto LABEL_14;
            case 0x116Fu:
              v10 = 704;
              v19 = "Connection failed, failed to get input handles. Error code: 0x%x.";
              goto LABEL_148;
            case 0x1170u:
              v7 = 79;
              v9 = "Disconnecting the session host Multipath transport did not receive acknowlegment from the peer. The c"
                   "lient may have been already closed.";
              a3 = 1;
              goto LABEL_14;
            case 0x1171u:
              v10 = 704;
              v19 = "Connection failed, Graphics caps not received (Logon error). Error code: 0x%x.";
              goto LABEL_148;
            case 0x1172u:
              v10 = 701;
              v9 = "The user's account has expired.";
              v7 = 80;
              goto LABEL_14;
            case 0x1173u:
              v7 = 82;
              v20 = Format;
              v10 = 701;
              v21 = "Token logon failed. Logon SubStatus code: 0x%x. Possible causes:\n"
                    "\n"
                    "1. The VM could not reach the Microsoft Entra ID authentication servers.\n"
                    "\n"
                    "2. Misconfigured multi-factor authentication enforcement.\n"
                    "The same restrictions should apply to both the client device and the Session Host VM.\n"
                    "Per-user multifactor authentication should be disabled.\n"
                    "For more information see: https://learn.microsoft.com/en-us/azure/virtual-desktop/set-up-mfa \n"
                    "\n"
                    "3. The user is not assigned a role required to login to the VM.\n"
                    "For more information see: https://learn.microsoft.com/en-us/entra/identity/devices/howto-vm-sign-in-"
                    "azure-ad-windows#configure-role-assignments-for-the-vm \n"
                    "\n"
                    "4. The VM is hybrid-joined and Password Replication is disabled for the user on the 'AzureADKerberos"
                    "' Domain Controller object.\n"
                    "For more information see: https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows"
                    "-server-2008-R2-and-2008/cc754646(v=ws.10)";
              v22 = 7;
              do
              {
                v23 = *((_OWORD *)v21 + 1);
                *(_OWORD *)v20 = *(_OWORD *)v21;
                v24 = *((_OWORD *)v21 + 2);
                *((_OWORD *)v20 + 1) = v23;
                v25 = *((_OWORD *)v21 + 3);
                *((_OWORD *)v20 + 2) = v24;
                v26 = *((_OWORD *)v21 + 4);
                *((_OWORD *)v20 + 3) = v25;
                v27 = *((_OWORD *)v21 + 5);
                *((_OWORD *)v20 + 4) = v26;
                v28 = *((_OWORD *)v21 + 6);
                *((_OWORD *)v20 + 5) = v27;
                v29 = *((_OWORD *)v21 + 7);
                v21 += 128;
                *((_OWORD *)v20 + 6) = v28;
                *((_OWORD *)v20 + 7) = v29;
                v20 += 128;
                --v22;
              }
              while ( v22 );
              v30 = *(_OWORD *)(v21 + 15);
              *(_OWORD *)v20 = *(_OWORD *)v21;
              *(_OWORD *)(v20 + 15) = v30;
              v31 = operator new[](0x3A7u);
              Block = v31;
              if ( v31 )
              {
                sprintf_s((char *const)v31, 0x3A7u, Format, a5);
                v9 = (char *)Block;
              }
              goto LABEL_14;
            case 0x1174u:
              v7 = 83;
              v9 = "Disconnecting the session host Multipath transport appears to hang on its read thread such that packe"
                   "ts received in the WinSock layer donot get to forwarded to the UDP transport layer";
              a3 = 1;
              goto LABEL_14;
            default:
              goto LABEL_296;
          }
        }
        v10 = 704;
        v19 = "Connection failed, can't create Input devices due to input bus ERROR_DEVICE_NOT_AVAILABLE (Logon error). E"
              "rror code: 0x%x.";
        goto LABEL_148;
      }
      if ( a2 <= 0x1182 )
      {
        if ( a2 == 4482 )
        {
          v10 = 708;
          v19 = "DirectStream transport disconnected due to media errors. Error code: 0x%x.";
          v7 = 120;
          goto LABEL_149;
        }
        if ( a2 == 4470 )
        {
          v7 = 84;
          v9 = "The session host lost connection to the client because of TURN server shutdown";
          goto LABEL_14;
        }
        if ( a2 != 4471 )
        {
          switch ( a2 )
          {
            case 0x117Cu:
              v10 = 708;
              v19 = "DirectStream transport disconnected due to a general error. Error code: 0x%x.";
              v7 = 116;
              break;
            case 0x117Du:
              v10 = 708;
              v19 = "DirectStream connection canceled due to timeout. Error code: 0x%x.";
              v7 = 114;
              break;
            case 0x117Eu:
              v7 = 115;
              v19 = "DirectStream connection timed out after attach. Error code: 0x%x.";
              break;
            case 0x117Fu:
              v10 = 708;
              v19 = "DirectStream transport disconnected due to a timeout. Error code: 0x%x.";
              v7 = 117;
              break;
            case 0x1180u:
              v10 = 708;
              v19 = "DirectStream transport disconnected due to general media errors. Error code: 0x%x.";
              v7 = 118;
              break;
            case 0x1181u:
              v7 = 119;
              v19 = "DirectStream transport disconnected due to connection media errors. Error code: 0x%x.";
              break;
            default:
              goto LABEL_296;
          }
          goto LABEL_149;
        }
        v19 = "Connection failed due to an error in the Multipath transport (SSPI). Error code: 0x%x.";
LABEL_148:
        v7 = 27;
        goto LABEL_149;
      }
      switch ( a2 )
      {
        case 0x1183u:
          v7 = 121;
          v19 = "DirectStream transport disconnected due to exceeded max call lifetime. Error code: 0x%x.";
          goto LABEL_149;
        case 0x1189u:
          v9 = "The session host lost connection to the client because of a write thread hang. ";
          v7 = 96;
          break;
        case 0x118Au:
          v7 = 95;
          v9 = "The session host lost connection to the client because of a write post incomplete. ";
          break;
        case 0x118Bu:
          v9 = "The session host lost connection to the client because of a write to winsock failed. ";
          v7 = 97;
          break;
        case 0x118Cu:
          a3 = 0;
          v9 = "User disconnected before completing logon. The connection was established but the user closed the client "
               "prior to reaching a logged on session.";
          v7 = 98;
          goto LABEL_14;
        case 0x1192u:
          v7 = 27;
          v9 = "Disconnect due to packet decryption failure.";
          goto LABEL_14;
        case 0x1193u:
          v7 = 27;
          v9 = "RDP failed to encrypt protocol data.";
          goto LABEL_14;
        default:
          goto LABEL_296;
      }
LABEL_187:
      v11 = 17000;
      goto LABEL_14;
    }
    if ( a2 <= 0x1283 )
    {
      if ( a2 == 4739 )
      {
        v10 = 708;
        v19 = "The session host lost connection to the client because of a server error in the Multipath websocket transp"
              "ort. Error code: 0x%x.";
        goto LABEL_148;
      }
      if ( a2 <= 0x1262 )
      {
        switch ( a2 )
        {
          case 0x1262u:
            v10 = 709;
            v19 = "The session host lost connection to the client because of a transport shutdown in the Multipath transp"
                  "ort. Error code: 0x%x.";
            goto LABEL_148;
          case 0x11F6u:
            v7 = 100;
            v9 = "Connection failed due to display protection License Issueing error.";
            goto LABEL_14;
          case 0x1259u:
            v7 = 27;
            v9 = "The session host lost connection to the client because of an internal error in the Multipath sockets transport stack.";
            v10 = 708;
            goto LABEL_14;
          case 0x125Du:
            v7 = 27;
            v9 = "Connection failed due to an invalid packet buffer size in the Multipath transport.";
            v10 = 709;
            goto LABEL_14;
        }
        if ( a2 != 4702 )
        {
          switch ( a2 )
          {
            case 0x125Fu:
              v10 = 708;
              v19 = "The session host lost connection to the client because of an invalid request in the Multipath transp"
                    "ort. Error code: 0x%x.";
              break;
            case 0x1260u:
              v7 = 86;
              v19 = "The session host lost connection to the client because of a timeout waiting for a response in the Mu"
                    "ltipath transport. Error code: 0x%x.";
              v10 = 708;
              goto LABEL_149;
            case 0x1261u:
              v10 = 708;
              v19 = "The session host lost connection to the client because of a request denied in the Multipath transpor"
                    "t. Error code: 0x%x.";
              break;
            default:
              goto LABEL_296;
          }
          goto LABEL_148;
        }
        v7 = 85;
LABEL_265:
        v10 = 709;
        v9 = "The session host lost connection to the client because of device not connected to the internet. Check your "
             "network quality and configurations, then try again.";
        goto LABEL_14;
      }
      switch ( a2 )
      {
        case 0x1263u:
          v7 = 88;
          v19 = "The session host lost connection to the client because of a connection cancelled in the Multipath transp"
                "ort. Error code: 0x%x.";
          v10 = 709;
          goto LABEL_149;
        case 0x1264u:
          v7 = 87;
          v9 = "The session host lost connection to the client because of a remote unreachable in the Multipath transport.";
          v10 = 708;
          goto LABEL_14;
        case 0x1265u:
          v7 = 89;
          v19 = "The session host lost connection to the client because of a remote reset in the Multipath transport. Error code: 0x%x.";
          v10 = 709;
          goto LABEL_149;
        case 0x1266u:
LABEL_188:
          v19 = "Connection failed due to an error in the Multipath transport. Error code: 0x%x.";
          goto LABEL_148;
      }
      if ( a2 != 4711 )
      {
        if ( a2 != 4737 )
        {
          if ( a2 == 4738 )
          {
            v7 = 27;
            v10 = 708;
            v9 = "The session host could not connect to the client because of a generic websocket error in the Multipath transport.";
            goto LABEL_14;
          }
          goto LABEL_296;
        }
        v7 = 90;
        v9 = "The session host lost connection to the client because of an unexpected network error in the Multipath webs"
             "ocket transport on the client side. Check your network quality and configurations, then try again.";
        goto LABEL_187;
      }
      v7 = 101;
LABEL_280:
      v10 = 708;
      v9 = "The session host lost connection to the client because of a network operation being blocked or modified. This"
           " can be due to a Personal Firewall interference.";
      goto LABEL_14;
    }
    if ( a2 > 0x10000001 )
      goto LABEL_296;
    if ( a2 == 268435457 )
    {
      v7 = 38;
      goto LABEL_13;
    }
    if ( a2 > 0x128C )
    {
      switch ( a2 )
      {
        case 0x128Du:
          v7 = 106;
          v19 = "The session host lost connection to the client because of a remote reset in the Multipath websocket tran"
                "sport. Error code: 0x%x.";
          v10 = 709;
          goto LABEL_149;
        case 0x128Eu:
          v19 = "Connection failed due to an error in the Multipath websocket transport. Error code: 0x%x.";
          goto LABEL_148;
        case 0x128Fu:
          v7 = 107;
          goto LABEL_280;
        case 0x1290u:
          v7 = 108;
          v9 = "The session host lost connection to the client because of a network data packet corruption in the Multipa"
               "th websocket transport. Your network connection may be unreliable.";
          v10 = 708;
          goto LABEL_14;
      }
      v32 = a2 - 4753;
      if ( a2 == 4753 )
      {
        v7 = 109;
        v10 = 708;
        v9 = "The session host Multipath websocket connection was denied by the web proxy. Make sure that the web proxy c"
             "onfiguration allows access to the AVD service.";
        goto LABEL_14;
      }
    }
    else
    {
      switch ( a2 )
      {
        case 0x128Cu:
          v7 = 104;
          v9 = "The session host lost connection to the client because of a remote unreachable in the Multipath websocket transport.";
          v10 = 708;
          goto LABEL_14;
        case 0x1284u:
          v7 = 27;
          v9 = "The session host lost connection to the client because of an unexpected error in the Multipath websocket "
               "transport websocket response.";
          v10 = 708;
          goto LABEL_14;
        case 0x1286u:
          v7 = 102;
          goto LABEL_265;
        case 0x1287u:
          v10 = 708;
          v19 = "The session host lost connection to the client because of an invalid request in the Multipath websocket "
                "transport. Error code: 0x%x.";
          goto LABEL_148;
        case 0x1288u:
          v7 = 103;
          v19 = "The session host lost connection to the client because of a timeout waiting for a response in the Multip"
                "ath websocket transport. Error code: 0x%x.";
          v10 = 708;
          goto LABEL_149;
        case 0x1289u:
          v10 = 708;
          v19 = "The session host lost connection to the client because of a request denied in the Multipath websocket tr"
                "ansport. Error code: 0x%x.";
          goto LABEL_148;
      }
      v32 = a2 - 4746;
      if ( a2 == 4746 )
      {
        v10 = 709;
        v19 = "The session host lost connection to the client because of a transport shutdown in the Multipath websocket "
              "transport. Error code: 0x%x.";
        goto LABEL_148;
      }
    }
    if ( v32 != 1 )
      goto LABEL_296;
    v7 = 105;
    v19 = "The session host lost connection to the client because of a connection cancelled in the Multipath websocket tr"
          "ansport. Error code: 0x%x.";
    v10 = 709;
LABEL_149:
    snprintf_s(Buffer, 0x104u, 0x103u, v19, a4);
    v9 = Buffer;
    goto LABEL_14;
  }
  if ( a2 == 256 )
    goto LABEL_84;
  if ( a2 > 0xD )
  {
    if ( a2 > 0x17 )
    {
      switch ( a2 )
      {
        case 0x18u:
          v9 = "Connection failed, Csrss process access failure.";
          goto LABEL_14;
        case 0x19u:
          v7 = 62;
          v38 = 1;
          v9 = "Connection closed due to server shutdown.";
          a3 = 1;
          goto LABEL_14;
        case 0x1Au:
          v7 = 63;
          v38 = 1;
          v9 = "Connection closed due to server reboot.";
          a3 = 1;
          goto LABEL_14;
        case 0x1Bu:
          v9 = "Connection failed, termservice is unable to process device PnP events or another major problem in termservice.";
          goto LABEL_14;
        case 0x1Cu:
          v38 = 1;
          v7 = 77;
          a3 = 1;
          v9 = "The session is locked and the user credentials are not suitable to unlock it locally. Reconnect is needed"
               " to unlock, disconnecting the session.";
          goto LABEL_14;
      }
    }
    else
    {
      switch ( a2 )
      {
        case 0x17u:
          v9 = "Connection failed, Winlogon process access failure.";
          goto LABEL_14;
        case 0xEu:
          v7 = 14;
          v9 = "The session host lost connection to the service because of an unexpected network error. Check your networ"
               "k quality and configurations, then try again.";
          v11 = 18000;
          goto LABEL_14;
        case 0xFu:
          v9 = "Connection failed, indirect display driver is not ready.";
          goto LABEL_14;
        case 0x10u:
          v9 = "Connection failed, DWM process access failure.";
          goto LABEL_14;
        case 0x11u:
          v9 = "Connection failed, indirect display driver failure.";
          goto LABEL_14;
        case 0x12u:
          v9 = "Connection failed, failure processing indirect display driver interface arrival event.";
          goto LABEL_14;
        case 0x13u:
          v9 = "Connection failed, processing Winlogon ConnectNotify event failed.";
          goto LABEL_14;
      }
    }
    goto LABEL_296;
  }
  if ( a2 == 13 )
  {
    a3 = 0;
    v38 = 1;
    v7 = 15;
    goto LABEL_14;
  }
  if ( a2 > 6 )
  {
    switch ( a2 )
    {
      case 7u:
        v7 = 17;
        v9 = "The session host doesn't have Remote Desktop access or has a policy that blocks access.";
        break;
      case 8u:
        v7 = 18;
        v9 = "Connection denied by server. FIPS was requested but server does not have it enabled.";
        break;
      case 9u:
        v7 = 19;
        v9 = "The user doesn't have access to the session host. The session host isn't configured to give this user Remot"
             "e Desktop access privileges.";
        break;
      case 0xAu:
        v7 = 20;
        v9 = "The server denied the connection because the session host configuration doesn't allow using saved credentials.";
        break;
      case 0xBu:
        a3 = 0;
        v38 = 1;
        v7 = 22;
        break;
      default:
        v38 = 1;
        v7 = 34;
        a3 = 0;
        break;
    }
    goto LABEL_14;
  }
  switch ( a2 )
  {
    case 6u:
      v7 = 32;
      v9 = "The user was disconnected because the session host memory was exhausted.";
      goto LABEL_14;
    case 0u:
      v38 = 1;
      v7 = 0;
      goto LABEL_14;
    case 1u:
      v7 = 37;
      goto LABEL_13;
  }
  if ( a2 != 2 )
  {
    if ( a2 == 3 )
    {
      v7 = 25;
    }
    else
    {
      if ( a2 == 4 )
      {
        v7 = 21;
        v9 = "The connection timed out due to network connection issues or session host overload.";
        goto LABEL_14;
      }
      v7 = 16;
    }
LABEL_13:
    v38 = 1;
    a3 = 1;
LABEL_14:
    v12 = v37;
    goto LABEL_15;
  }
  v7 = 0;
  v38 = 1;
  a3 = 1;
  v12 = 1;
LABEL_15:
  v13 = *((_DWORD *)v40 + 210);
  if ( v38 )
  {
    if ( v13 )
    {
      v14 = 3;
      if ( a3 )
        v14 = (unsigned int)v12;
      v48 = *(_OWORD *)((char *)v40 + 808);
      RDPServerStackDiagnostics_LogDisconnect(&v48, v14, v7);
    }
    if ( (unsigned int)dword_1801B76C8 > 3 )
    {
      v40 = (CUMRDPConnection *)v9;
      SymbolicNameFromCode = RDPServerStackDiagnostics_GetSymbolicNameFromCode(v7, a2, v12);
      v39 = v7;
      v42 = SymbolicNameFromCode;
      v38 = a3 != 0;
      v41 = "Successful Disconnect";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v16,
        (unsigned int)&dword_180196EB4,
        v17,
        v18,
        (__int64)&v41,
        (__int64)&v38,
        (__int64)&v39,
        (__int64)&v42,
        (__int64)&v40);
    }
  }
  else
  {
    if ( v13 )
    {
      v48 = *(_OWORD *)((char *)v40 + 808);
      RDPServerStackDiagnostics_LogFailure(&v48, v10, v7, a2, v9, v11, 1, 7);
    }
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v44 = v9;
      v33 = RDPServerStackDiagnostics_GetSymbolicNameFromCode(v7, a2, v12);
      v39 = v7;
      v45 = v33;
      v38 = v10;
      v37 = a2;
      LODWORD(v42) = 2596;
      LODWORD(v41) = a3 != 0;
      v46 = "LogDisconnectDiagnosticsEvent";
      v47 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdpimpl.cpp";
      *(_QWORD *)&v48 = "RDP disconnect RDPServerStackDiagnostics_LogFailure";
      LODWORD(v40) = a4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v34,
        (unsigned int)byte_180196DFD,
        v35,
        v36,
        (__int64)&v48,
        (__int64)&v40,
        (__int64)&v47,
        (__int64)&v42,
        (__int64)&v46,
        (__int64)&v41,
        (__int64)&v37,
        (__int64)&v38,
        (__int64)&v39,
        (__int64)&v45,
        (__int64)&v44);
    }
  }
  if ( Block )
    operator delete(Block);
}

```

## disassembly

```asm
0x18004c178  mov     [rsp-8+arg_10], rbx
0x18004c17d  push    rbp
0x18004c17e  push    rsi
0x18004c17f  push    rdi
0x18004c180  push    r12
0x18004c182  push    r13
0x18004c184  push    r14
0x18004c186  push    r15
0x18004c188  lea     rbp, [rsp-4A0h]
0x18004c190  sub     rsp, 5A0h
0x18004c197  mov     rax, cs:__security_cookie
0x18004c19e  xor     rax, rsp
0x18004c1a1  mov     [rbp+4D0h+var_40], rax
0x18004c1a8  mov     r12d, r8d
0x18004c1ab  mov     [rbp+4D0h+var_540], rcx
0x18004c1af  mov     r14d, edx
0x18004c1b2  mov     [rbp+4D0h+var_54C], 0
0x18004c1b9  mov     ebx, 1Ah
0x18004c1be  mov     [rbp+4D0h+var_550], 2
0x18004c1c5  xor     edx, edx; Val
0x18004c1c7  mov     [rbp+4D0h+var_548], ebx
0x18004c1ca  mov     r8d, 104h; Size
0x18004c1d0  lea     rcx, [rbp+4D0h+Buffer]; void *
0x18004c1d4  mov     r15d, r9d
0x18004c1d7  lea     rsi, aConnectionFail_46; "Connection failed, see disconnect code "...
0x18004c1de  mov     edi, 309h
0x18004c1e3  call    memset_0
0x18004c1e8  xor     eax, eax
0x18004c1ea  xor     r13d, r13d
0x18004c1ed  mov     [rbp+4D0h+Block], rax
0x18004c1f1  mov     eax, 100h
0x18004c1f6  cmp     r14d, eax
0x18004c1f9  ja      loc_18004C535
0x18004c1ff  jz      loc_18004C623
0x18004c205  cmp     r14d, 0Dh
0x18004c209  ja      loc_18004C420
0x18004c20f  jz      loc_18004C40C
0x18004c215  cmp     r14d, 6
0x18004c219  ja      loc_18004C381
0x18004c21f  jz      loc_18004C370
0x18004c225  mov     eax, r14d
0x18004c228  test    r14d, r14d
0x18004c22b  jz      loc_18004C362
0x18004c231  sub     eax, 1
0x18004c234  jz      loc_18004C358
0x18004c23a  sub     eax, 1
0x18004c23d  jz      loc_18004C343
0x18004c243  sub     eax, 1
0x18004c246  jz      loc_18004C339
0x18004c24c  sub     eax, 1
0x18004c24f  jz      loc_18004C328
0x18004c255  cmp     eax, 1
0x18004c258  jnz     def_18004C980; jumptable 000000018004C980 default case, cases 4431,4432
0x18004c25e  lea     ebx, [rax+0Fh]
0x18004c261  mov     [rbp+4D0h+var_54C], 1
0x18004c268  mov     r12d, 1
0x18004c26e  mov     r8d, [rbp+4D0h+var_550]
0x18004c272  cmp     [rbp+4D0h+var_54C], 0
0x18004c276  mov     rcx, [rbp+4D0h+var_540]
0x18004c27a  mov     eax, [rcx+348h]
0x18004c280  jz      loc_18004D36C
0x18004c286  test    eax, eax
0x18004c288  jz      short loc_18004C2AF
0x18004c28a  movups  xmm0, xmmword ptr [rcx+328h]
0x18004c291  test    r12d, r12d
0x18004c294  lea     rcx, [rbp+4D0h+var_500]
0x18004c298  mov     edx, 3
0x18004c29d  cmovnz  edx, r8d
0x18004c2a1  mov     r8d, ebx
0x18004c2a4  movdqu  [rbp+4D0h+var_500], xmm0
0x18004c2a9  call    cs:__imp_RDPServerStackDiagnostics_LogDisconnect
0x18004c2af  mov     eax, cs:dword_1801B76C8
0x18004c2b5  cmp     eax, 3
0x18004c2b8  jbe     loc_18004D477
0x18004c2be  mov     edx, r14d
0x18004c2c1  mov     [rbp+4D0h+var_540], rsi
0x18004c2c5  mov     ecx, ebx
0x18004c2c7  call    cs:__imp_RDPServerStackDiagnostics_GetSymbolicNameFromCode
0x18004c2cd  lea     rdx, dword_180196EB4
0x18004c2d4  mov     [rbp+4D0h+var_548], ebx
0x18004c2d7  mov     [rbp+4D0h+var_530], rax
0x18004c2db  xor     eax, eax
0x18004c2dd  test    r12d, r12d
0x18004c2e0  setnz   al
0x18004c2e3  mov     [rbp+4D0h+var_54C], eax
0x18004c2e6  lea     rax, aSuccessfulDisc; "Successful Disconnect"
0x18004c2ed  mov     [rbp+4D0h+var_538], rax
0x18004c2f1  lea     rax, [rbp+4D0h+var_540]
0x18004c2f5  mov     [rsp+5D0h+var_590], rax
0x18004c2fa  lea     rax, [rbp+4D0h+var_530]
0x18004c2fe  mov     [rsp+5D0h+var_598], rax
0x18004c303  lea     rax, [rbp+4D0h+var_548]
0x18004c307  mov     [rsp+5D0h+var_5A0], rax
0x18004c30c  lea     rax, [rbp+4D0h+var_54C]
0x18004c310  mov     [rsp+5D0h+var_5A8], rax
0x18004c315  lea     rax, [rbp+4D0h+var_538]
0x18004c319  mov     [rsp+5D0h+var_5B0], rax
0x18004c31e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18004c323  jmp     loc_18004D477
0x18004c328  mov     ebx, 15h
0x18004c32d  lea     rsi, aTheConnectionT; "The connection timed out due to network"...
0x18004c334  jmp     loc_18004C26E
0x18004c339  mov     ebx, 19h
0x18004c33e  jmp     loc_18004C261
0x18004c343  xor     ebx, ebx
0x18004c345  mov     [rbp+4D0h+var_54C], 1
0x18004c34c  lea     r12d, [rbx+1]
0x18004c350  mov     r8d, r12d
0x18004c353  jmp     loc_18004C272
0x18004c358  mov     ebx, 25h ; '%'
0x18004c35d  jmp     loc_18004C261
0x18004c362  mov     [rbp+4D0h+var_54C], 1
0x18004c369  xor     ebx, ebx
0x18004c36b  jmp     loc_18004C26E
0x18004c370  mov     ebx, 20h ; ' '
0x18004c375  lea     rsi, aTheUserWasDisc; "The user was disconnected because the s"...
0x18004c37c  jmp     loc_18004C26E
0x18004c381  mov     eax, r14d
0x18004c384  sub     eax, 7
0x18004c387  jz      short loc_18004C3FB
0x18004c389  sub     eax, 1
0x18004c38c  jz      short loc_18004C3EA
0x18004c38e  sub     eax, 1
0x18004c391  jz      short loc_18004C3D9
0x18004c393  sub     eax, 1
0x18004c396  jz      short loc_18004C3C8
0x18004c398  sub     eax, 1
0x18004c39b  jz      short loc_18004C3B4
0x18004c39d  cmp     eax, 1
0x18004c3a0  jnz     def_18004C980; jumptable 000000018004C980 default case, cases 4431,4432
0x18004c3a6  mov     [rbp+4D0h+var_54C], eax
0x18004c3a9  lea     ebx, [rax+21h]
0x18004c3ac  xor     r12d, r12d
0x18004c3af  jmp     loc_18004C26E
0x18004c3b4  xor     r12d, r12d
0x18004c3b7  mov     [rbp+4D0h+var_54C], 1
0x18004c3be  lea     ebx, [r12+16h]
0x18004c3c3  jmp     loc_18004C26E
0x18004c3c8  mov     ebx, 14h
0x18004c3cd  lea     rsi, aTheServerDenie; "The server denied the connection becaus"...
0x18004c3d4  jmp     loc_18004C26E
0x18004c3d9  mov     ebx, 13h
0x18004c3de  lea     rsi, aTheUserDoesnTH; "The user doesn't have access to the ses"...
0x18004c3e5  jmp     loc_18004C26E
0x18004c3ea  mov     ebx, 12h
0x18004c3ef  lea     rsi, aConnectionDeni; "Connection denied by server. FIPS was r"...
0x18004c3f6  jmp     loc_18004C26E
0x18004c3fb  mov     ebx, 11h
0x18004c400  lea     rsi, aTheSessionHost_32; "The session host doesn't have Remote De"...
0x18004c407  jmp     loc_18004C26E
0x18004c40c  xor     r12d, r12d
0x18004c40f  mov     [rbp+4D0h+var_54C], 1
0x18004c416  lea     ebx, [r12+0Fh]
0x18004c41b  jmp     loc_18004C26E
0x18004c420  cmp     r14d, 17h
0x18004c424  ja      loc_18004C4B0
0x18004c42a  jz      short loc_18004C4A4
0x18004c42c  mov     eax, r14d
0x18004c42f  sub     eax, 0Eh
0x18004c432  jz      short loc_18004C48D
0x18004c434  sub     eax, 1
0x18004c437  jz      short loc_18004C481
0x18004c439  sub     eax, 1
0x18004c43c  jz      short loc_18004C475
0x18004c43e  sub     eax, 1
0x18004c441  jz      short loc_18004C469
0x18004c443  sub     eax, 1
0x18004c446  jz      short loc_18004C45D
0x18004c448  cmp     eax, 1
0x18004c44b  jnz     def_18004C980; jumptable 000000018004C980 default case, cases 4431,4432
0x18004c451  lea     rsi, aConnectionFail_31; "Connection failed, processing Winlogon "...
0x18004c458  jmp     loc_18004C26E
0x18004c45d  lea     rsi, aConnectionFail; "Connection failed, failure processing i"...
0x18004c464  jmp     loc_18004C26E
0x18004c469  lea     rsi, aConnectionFail_11; "Connection failed, indirect display dri"...
0x18004c470  jmp     loc_18004C26E
0x18004c475  lea     rsi, aConnectionFail_19; "Connection failed, DWM process access f"...
0x18004c47c  jmp     loc_18004C26E
0x18004c481  lea     rsi, aConnectionFail_9; "Connection failed, indirect display dri"...
0x18004c488  jmp     loc_18004C26E
0x18004c48d  mov     ebx, 0Eh
0x18004c492  lea     rsi, aTheSessionHost_10; "The session host lost connection to the"...
0x18004c499  mov     r13d, 4650h
0x18004c49f  jmp     loc_18004C26E
0x18004c4a4  lea     rsi, aConnectionFail_22; "Connection failed, Winlogon process acc"...
0x18004c4ab  jmp     loc_18004C26E
0x18004c4b0  mov     eax, r14d
0x18004c4b3  sub     eax, 18h
0x18004c4b6  jz      short loc_18004C529
0x18004c4b8  sub     eax, 1
0x18004c4bb  jz      short loc_18004C50D
0x18004c4bd  sub     eax, 1
0x18004c4c0  jz      short loc_18004C4F1
0x18004c4c2  sub     eax, 1
0x18004c4c5  jz      short loc_18004C4E5
0x18004c4c7  cmp     eax, 1
0x18004c4ca  jnz     def_18004C980; jumptable 000000018004C980 default case, cases 4431,4432
0x18004c4d0  mov     [rbp+4D0h+var_54C], eax
0x18004c4d3  lea     ebx, [rax+4Ch]
0x18004c4d6  mov     r12d, eax
0x18004c4d9  lea     rsi, aTheSessionIsLo; "The session is locked and the user cred"...
0x18004c4e0  jmp     loc_18004C26E
0x18004c4e5  lea     rsi, aConnectionFail_4; "Connection failed, termservice is unabl"...
0x18004c4ec  jmp     loc_18004C26E
0x18004c4f1  mov     ebx, 3Fh ; '?'
0x18004c4f6  mov     [rbp+4D0h+var_54C], 1
0x18004c4fd  lea     rsi, aConnectionClos_0; "Connection closed due to server reboot."
0x18004c504  lea     r12d, [rbx-3Eh]
0x18004c508  jmp     loc_18004C26E
0x18004c50d  mov     ebx, 3Eh ; '>'
0x18004c512  mov     [rbp+4D0h+var_54C], 1
0x18004c519  lea     rsi, aConnectionClos; "Connection closed due to server shutdow"...
0x18004c520  lea     r12d, [rbx-3Dh]
0x18004c524  jmp     loc_18004C26E
0x18004c529  lea     rsi, aConnectionFail_28; "Connection failed, Csrss process access"...
0x18004c530  jmp     loc_18004C26E
0x18004c535  mov     eax, 400h
0x18004c53a  cmp     r14d, eax
0x18004c53d  ja      loc_18004C639
0x18004c543  jz      loc_18004C6D9
0x18004c549  mov     eax, 106h
0x18004c54e  cmp     r14d, eax
0x18004c551  ja      short loc_18004C5C1
0x18004c553  jz      loc_18004C623
0x18004c559  mov     eax, r14d
0x18004c55c  sub     eax, 101h
0x18004c561  jz      short loc_18004C5AB
0x18004c563  sub     eax, 1
0x18004c566  jz      short loc_18004C595
0x18004c568  sub     eax, 1
0x18004c56b  jz      loc_18004C623
0x18004c571  sub     eax, 1
0x18004c574  jz      short loc_18004C57F
0x18004c576  cmp     eax, 1
0x18004c579  jnz     def_18004C980; jumptable 000000018004C980 default case, cases 4431,4432
0x18004c57f  mov     edi, 2BEh
0x18004c584  lea     rsi, aConnectionFail_14; "Connection failed due to an invalid lic"...
0x18004c58b  mov     ebx, 1Eh
0x18004c590  jmp     loc_18004C26E
0x18004c595  mov     edi, 2BEh
0x18004c59a  lea     rsi, aConnectionFail_49; "Connection failed because a license is "...
0x18004c5a1  mov     ebx, 0Dh
0x18004c5a6  jmp     loc_18004C26E
0x18004c5ab  mov     edi, 2BEh
0x18004c5b0  lea     rsi, aTheSessionHost_3; "The session host licensing information "...
0x18004c5b7  mov     ebx, 1Ch
0x18004c5bc  jmp     loc_18004C26E
0x18004c5c1  mov     eax, r14d
0x18004c5c4  sub     eax, 107h
0x18004c5c9  jz      short loc_18004C623
0x18004c5cb  sub     eax, 1
0x18004c5ce  jz      short loc_18004C623
0x18004c5d0  sub     eax, 1
0x18004c5d3  jz      short loc_18004C60D
0x18004c5d5  sub     eax, 1
0x18004c5d8  jz      short loc_18004C5F7
0x18004c5da  cmp     eax, 1
0x18004c5dd  jnz     def_18004C980; jumptable 000000018004C980 default case, cases 4431,4432
0x18004c5e3  mov     edi, 2BEh
0x18004c5e8  lea     ebx, [rax+23h]
0x18004c5eb  lea     rsi, aAccessDeniedWh; "Access denied when trying to recreate t"...
0x18004c5f2  jmp     loc_18004C26E
0x18004c5f7  mov     edi, 2BEh
0x18004c5fc  lea     rsi, aConnectionDeni_0; "Connection denied due to licensing. Ser"...
0x18004c603  mov     ebx, 1Dh
0x18004c608  jmp     loc_18004C26E
0x18004c60d  mov     edi, 2BEh
0x18004c612  lea     rsi, aCanTUpgradeLic; "Can't upgrade license. The requested li"...
0x18004c619  mov     ebx, 23h ; '#'
0x18004c61e  jmp     loc_18004C26E
0x18004c623  mov     edi, 2BEh
0x18004c628  lea     rsi, aConnectionFail_48; "Connection failed due to a license proc"...
0x18004c62f  mov     ebx, 1Fh
0x18004c634  jmp     loc_18004C26E
0x18004c639  mov     eax, 1163h
0x18004c63e  cmp     r14d, eax
0x18004c641  ja      loc_18004CC15
0x18004c647  jz      loc_18004CC04
0x18004c64d  mov     eax, 113Fh
0x18004c652  cmp     r14d, eax
0x18004c655  ja      loc_18004C95F
0x18004c65b  jz      loc_18004C949
0x18004c661  mov     eax, 10DEh
0x18004c666  cmp     r14d, eax
0x18004c669  ja      loc_18004C795
0x18004c66f  jz      loc_18004C784
0x18004c675  mov     eax, 411h
0x18004c67a  cmp     r14d, eax
0x18004c67d  ja      short loc_18004C6EA
0x18004c67f  jz      loc_18004C778
0x18004c685  mov     eax, r14d
0x18004c688  sub     eax, 402h
0x18004c68d  jz      short loc_18004C6D9
0x18004c68f  sub     eax, 2
0x18004c692  jz      short loc_18004C6D9
0x18004c694  sub     eax, 1
0x18004c697  jz      loc_18004C778
0x18004c69d  sub     eax, 1
0x18004c6a0  jz      loc_18004C778
0x18004c6a6  sub     eax, 1
  ... truncated ...
```
