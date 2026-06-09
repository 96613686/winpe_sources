# Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::.cctor

- ea: `0x4d360`
- end: `0x4d537`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::.cctor`
- size: `471`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x4d360`: `EmailConnectorIncomingEmailMailboxId`
- `0x4d36a`: `EmailConnectorIncomingEmailsRetrieved`
- `0x4d374`: `EmailConnectorIncomingEmailsDelivered`
- `0x4d3a6`: `EmailConnectorIncomingEmailEwsHost`
- `0x4d3b0`: `EmailConnectorIncomingEmailEwsPort`
- `0x4d3ba`: `EmailConnectorIncomingEmailEwsBytesReceived`
- `0x4d3c4`: `EmailConnectorIncomingEmailEwsBytesSent`
- `0x4d3ce`: `EmailConnectorIncomingEmailEwsConnections`
- `0x4d3d8`: `EmailConnectorIncomingEmailEwsTotalConnectionTime`
- `0x4d41e`: `EmailConnectorIncomingEmailPop3Host`
- `0x4d428`: `EmailConnectorIncomingEmailPop3Port`
- `0x4d432`: `EmailConnectorIncomingEmailPop3BytesReceived`
- `0x4d43c`: `EmailConnectorIncomingEmailPop3BytesSent`
- `0x4d446`: `EmailConnectorIncomingEmailPop3Connections`
- `0x4d450`: `EmailConnectorIncomingEmailPop3TotalConnectionTime`
- `0x4d496`: `ExchangeIncomingEmailTrafficMonitorEvent`
- `0x4d4aa`: `Pop3IncomingEmailTrafficMonitorEvent`
- `0x4d4dc`: `ExchangeTaskTrafficMonitorEvent`

## pseudocode

```c

```

## disassembly

```asm
0x4d360  ldstr    aEmailconnector_3// "EmailConnectorIncomingEmailMailboxId"
0x4d365  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailMailboxId
0x4d36a  ldstr    aEmailconnector_4// "EmailConnectorIncomingEmailsRetrieved"
0x4d36f  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailsRetrieved
0x4d374  ldstr    aEmailconnector_5// "EmailConnectorIncomingEmailsDelivered"
0x4d379  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailsDelivered
0x4d37e  ldstr    aEmailconnector_6// "EmailConnectorOutgoingEmailId"
0x4d383  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailId
0x4d388  ldstr    aEmailconnector_7// "EmailConnectorOutgoingEmailsSent"
0x4d38d  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailsSent
0x4d392  ldstr    aEmailconnector_8// "EmailConnectorOutgoingEmailsProcessed"
0x4d397  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailsProcessed
0x4d39c  ldstr    aEmailconnector_9// "EmailConnectorOutgoingEmailSmtpBytesSen"...
0x4d3a1  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailSmtpBytesSent
0x4d3a6  ldstr    aEmailconnector_10// "EmailConnectorIncomingEmailEwsHost"
0x4d3ab  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailEwsHost
0x4d3b0  ldstr    aEmailconnector_11// "EmailConnectorIncomingEmailEwsPort"
0x4d3b5  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailEwsPort
0x4d3ba  ldstr    aEmailconnector_12// "EmailConnectorIncomingEmailEwsBytesRece"...
0x4d3bf  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailEwsBytesReceived
0x4d3c4  ldstr    aEmailconnector_13// "EmailConnectorIncomingEmailEwsBytesSent"
0x4d3c9  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailEwsBytesSent
0x4d3ce  ldstr    aEmailconnector_14// "EmailConnectorIncomingEmailEwsConnectio"...
0x4d3d3  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailEwsConnections
0x4d3d8  ldstr    aEmailconnector_15// "EmailConnectorIncomingEmailEwsTotalConn"...
0x4d3dd  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailEwsTotalConnectionTime
0x4d3e2  ldstr    aEmailconnector_16// "EmailConnectorOutgoingEmailEwsHost"
0x4d3e7  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailEwsHost
0x4d3ec  ldstr    aEmailconnector_17// "EmailConnectorOutgoingEmailEwsPort"
0x4d3f1  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailEwsPort
0x4d3f6  ldstr    aEmailconnector_18// "EmailConnectorOutgoingEmailEwsBytesRece"...
0x4d3fb  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailEwsBytesReceived
0x4d400  ldstr    aEmailconnector_19// "EmailConnectorOutgoingEmailEwsBytesSent"
0x4d405  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailEwsBytesSent
0x4d40a  ldstr    aEmailconnector_20// "EmailConnectorOutgoingEmailEwsConnectio"...
0x4d40f  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailEwsConnections
0x4d414  ldstr    aEmailconnector_21// "EmailConnectorOutgoingEmailEwsTotalConn"...
0x4d419  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailEwsTotalConnectionTime
0x4d41e  ldstr    aEmailconnector_22// "EmailConnectorIncomingEmailPop3Host"
0x4d423  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailPop3Host
0x4d428  ldstr    aEmailconnector_23// "EmailConnectorIncomingEmailPop3Port"
0x4d42d  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailPop3Port
0x4d432  ldstr    aEmailconnector_24// "EmailConnectorIncomingEmailPop3BytesRec"...
0x4d437  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailPop3BytesReceived
0x4d43c  ldstr    aEmailconnector_25// "EmailConnectorIncomingEmailPop3BytesSen"...
0x4d441  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailPop3BytesSent
0x4d446  ldstr    aEmailconnector_26// "EmailConnectorIncomingEmailPop3Connecti"...
0x4d44b  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailPop3Connections
0x4d450  ldstr    aEmailconnector_27// "EmailConnectorIncomingEmailPop3TotalCon"...
0x4d455  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailPop3TotalConnectionTime
0x4d45a  ldstr    aEmailconnector_28// "EmailConnectorOutgoingEmailSMTPHost"
0x4d45f  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailSMTPHost
0x4d464  ldstr    aEmailconnector_29// "EmailConnectorOutgoingEmailSMTPPort"
0x4d469  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailSMTPPort
0x4d46e  ldstr    aEmailconnector_30// "EmailConnectorOutgoingEmailSMTPBytesRec"...
0x4d473  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailSMTPBytesReceived
0x4d478  ldstr    aEmailconnector_31// "EmailConnectorOutgoingEmailSMTPBytesSen"...
0x4d47d  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailSMTPBytesSent
0x4d482  ldstr    aEmailconnector_32// "EmailConnectorOutgoingEmailSMTPConnecti"...
0x4d487  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailSMTPConnections
0x4d48c  ldstr    aEmailconnector_33// "EmailConnectorOutgoingEmailSMTPTotalCon"...
0x4d491  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorOutgoingEmailSMTPTotalConnectionTime
0x4d496  ldstr    aExchangeincomi// "ExchangeIncomingEmailTrafficMonitorEven"...
0x4d49b  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::ExchangeIncomingEmailTrafficMonitorEvent
0x4d4a0  ldstr    aExchangeoutgoi// "ExchangeOutgoingEmailTrafficMonitorEven"...
0x4d4a5  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::ExchangeOutgoingEmailTrafficMonitorEvent
0x4d4aa  ldstr    aPop3incomingem// "Pop3IncomingEmailTrafficMonitorEvent"
0x4d4af  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::Pop3IncomingEmailTrafficMonitorEvent
0x4d4b4  ldstr    aSmtpoutgoingem// "SmtpOutgoingEmailTrafficMonitorEvent"
0x4d4b9  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::SmtpOutgoingEmailTrafficMonitorEvent
0x4d4be  ldstr    aExchangeacttra// "ExchangeACTTrafficMonitorEvent"
0x4d4c3  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::ExchangeACTTrafficMonitorEvent
0x4d4c8  ldstr    aExchangeappoin// "ExchangeAppointmentTrafficMonitorEvent"
0x4d4cd  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::ExchangeAppointmentTrafficMonitorEvent
0x4d4d2  ldstr    aExchangecontac// "ExchangeContactTrafficMonitorEvent"
0x4d4d7  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::ExchangeContactTrafficMonitorEvent
0x4d4dc  ldstr    aExchangetasktr// "ExchangeTaskTrafficMonitorEvent"
0x4d4e1  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::ExchangeTaskTrafficMonitorEvent
0x4d4e6  ldstr    aErrorscope// "ErrorScope"
0x4d4eb  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::ErrorScope
0x4d4f0  ldstr    aServererrorcod// "ServerErrorCode"
0x4d4f5  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::ServerErrorCode
0x4d4fa  ldstr    aErrorsource// "ErrorSource"
0x4d4ff  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::ErrorSource
0x4d504  ldstr    aErrortype// "ErrorType"
0x4d509  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::ErrorType
0x4d50e  ldstr    aMachinename// "MachineName"
0x4d513  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::MachineName
0x4d518  ldstr    aCrmtracecode// "CRMTraceCode"
0x4d51d  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::CRMTraceCode
0x4d522  ldstr    aTracesnippet// "TraceSnippet"
0x4d527  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::TraceSnippet
0x4d52c  ldstr    aInvalidevent// "InvalidEvent"
0x4d531  stsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::InvalidEvent
0x4d536  ret
```
